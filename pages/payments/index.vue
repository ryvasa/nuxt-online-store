<template>
  <div class="flex flex-col justify-center items-center p-20">
    <div id="snap-container"></div>
    <div class="flex flex-col gap-5 w-96 justify-center items-center p-5">
      <h1 class="text-3xl">Payments</h1>

      <label>Payment Methodes</label>
      <select
        class="select border-2 dark:bg-gray-800 w-full"
        @change="handlePaymentChange"
      >
        <option disabled selected>Pick Payment</option>
        <option value="credit-debit">Credit or Debit</option>
        <option value="atm-bank-transfer">ATM or Bank Transfer</option>
        <option value="e-wallet">E-Wallet</option>
      </select>

      <form
        class="flex flex-col gap-4 w-full text-sm"
        action=""
        v-if="payment_type === 'credit-debit'"
      >
        <div class="flex flex-col gap-1">
          <label for="card_number">Card Number</label>
          <input
            placeholder="1234 1234 1234 1234"
            id="card_number"
            class="input dark:bg-gray-800 w-full text-sm"
            type="text"
          />
        </div>
        <div class="flex justify-between gap-4">
          <div class="flex flex-col gap-1 flex-1">
            <label for="expiration_date">Expiration Date</label>
            <input
              placeholder="MM/YY"
              id="expiration_date"
              class="input dark:bg-gray-800 w-full text-sm"
              type="text"
            />
          </div>
          <div class="flex flex-col gap-1 flex-1">
            <label for="cvv">CVV</label>
            <input
              placeholder="123"
              id="cvv"
              class="input dark:bg-gray-800 w-full text-sm"
              type="text"
            />
          </div>
        </div>
      </form>

      <select
        @change="handleBankChange"
        v-if="payment_type === 'atm-bank-transfer'"
        class="select w-full border-2 dark:bg-gray-800"
      >
        <option disabled selected>Pick Bank</option>
        <option value="bca">BCA</option>
        <option value="bni">BNI</option>
        <option value="bri">BRI</option>
        <option value="mandiri">Mandiri</option>
        <option value="permata">Permata</option>
      </select>

      <select
        @change="handleEWalletChange"
        v-if="payment_type === 'e-wallet'"
        class="select w-full border-2 dark:bg-gray-800"
      >
        <option disabled selected>Pick E-Wallet</option>
        <option value="gopay">Gopay</option>
        <option value="shopepay">Shopepay</option>
        <option value="ovo">Ovo</option>
        <option value="dana">Dana</option>
      </select>
    </div>
    <button v-on:click="handleClick" class="btn btn-primary">Pay</button>
  </div>
</template>
<script setup lang="ts">
const payment_type = ref('');
const bank_transfer = ref('');
const e_wallet = ref('');
const item_details = ref([]);
const adderess = ref('');

const handlePaymentChange = (e: Event) => {
  const target = e.target as HTMLSelectElement;
  payment_type.value = target.value;
};

const handleBankChange = (e: Event) => {
  const target = e.target as HTMLSelectElement;
  bank_transfer.value = target.value;
};

const handleEWalletChange = (e: Event) => {
  const target = e.target as HTMLSelectElement;
  e_wallet.value = target.value;
};

interface TransactionResponse {
  data: {
    payment: {
      token: string;
      redirect_url: string;
    };
  };
}
const handleClick = async () => {
  const { data, error } = await useFetch<TransactionResponse | null>(
    'http://localhost:3000/transactions',
    {
      method: 'POST',
      headers: {
        Authorization:
          'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6ImI3MjAxMWEwLTFlYjYtNDg5MC05ZTNkLWZiNTU1Y2YyODA0ZiIsInVzZXJuYW1lIjoiam9obmRvZSIsImlhdCI6MTcyNDYzOTM3MywiZXhwIjoxNzI0NzI1NzczfQ.YlqvbeN6l045byp3KeZLoStjRhrw_nv23ZLAMmXtI-4',
      },
      body: {
        address: 'jalan jalan',
        items: [
          {
            product: '66c9c2be3799102c7634872a',
            stock: '66c9c2e93799102c7634872c',
            quantity: '2',
          },
        ],
      },
    }
  );

  console.log(data.value?.data.payment.redirect_url);
};
</script>

<style>
/* Tambahkan style jika diperlukan */
</style>
