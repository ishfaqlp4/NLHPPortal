(function() {
  const script = document.createElement('script');


  script.src = "https://cdn.aws.billingplatform.com/hosted-payments-ui@release/lib.js";

  document.body.append(script);
  script.onload = function () {
    HostedPayments.renderPaymentForm({
      /** Required parameters: */
  
      // Specify css selector where you want to show payment widget
      targetSelector: 'body',

      // Specify payment amount
      amount: 100,

      // Specify environment ID
      environmentId: 'environment ID',

      // Specify billing profile ID
      billingProfileId: 'billing profile ID',

      // Specify gateway names
      paymentGateways: ['Adyen_CC', 'Adyen_DD'],

      /** Additional parameters: */
      walletMode: true,
      allowEditPrice: true,
      fullName: 'John',
      state: 'CO' 
    });
  };
})();
