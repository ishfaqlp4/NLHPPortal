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
      environmentId: '096602aa-a033-4dad-815d-754105dbf6fc',

      // Specify billing profile ID
      billingProfileId: '1ba91f19-61f9-1c28-e063-ee043c0a3abe',

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
