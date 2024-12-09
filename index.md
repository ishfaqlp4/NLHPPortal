html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>HPP Test Button Click</title>
</head>
<body>
  <button id="executeButton">Click Me</button>

  <script>
    document.getElementById('executeButton').addEventListener('click', function() {
      const script = document.createElement('script');

  // Use hosted-payments-ui@1.0.0 to apply exact widget version
  // Or hosted-payments-ui@1 to apply last version from specified version
  script.src = "https://cdn.aws.billingplatform.com/hosted-payments-ui@1/lib.js";

  document.body.append(script);
  script.onload = function () {
    HostedPayments.renderPaymentForm({
      /** Required parameters: */
      securityToken: "eyJhbGciOiJIUzUxMiJ9.eyJlbnZpcm9ubWVudElkIjoiMDk2NjAyYWEtYTAzMy00ZGFkLTgxNWQtNzU0MTA1ZGJmNmZjIiwiY2xpZW50SWQiOiJ1dGtLS2Q4VEQyN05xcFY5OGJtWVloYzhXNlI0YkJ1NiIsInVzZXJJZCI6IjYiLCJ1c2VybmFtZSI6ImJ0ZXN0Iiwicm9sZXMiOlsiQURNSU4iXSwiVG9rZW5UeXBlIjoiQUNDRVNTIiwiaWF0IjoxNzMzNDM0ODk4LCJleHAiOjE3MzM1MTc2OTh9._JPVnaStg6lu5zW0-JgfN_L__93OvaPjt0Oj7O1B4ex6O_8B2L-sEep55qoN7fewEwhsuJOacQOZU6dUstTaJw",
      
      apiUrl: "https://sandbox.billingplatform.com/noonlight_dev/hostedPayments/1.0/",
      // Specify css selector where you want to show payment widget
      targetSelector: 'body',

      // Specify payment amount
      amount: 100,

      // Specify environment ID
      environmentId: '096602aa-a033-4dad-815d-754105dbf6fc',

      // Specify billing profile ID
      billingProfileId: '1ba91f19-61f9-1c28-e063-ee043c0a3abe',

      // Specify gateway names
      paymentGateways: ['CreditCard', 'ACH'],

      /** Additional parameters: */
      // walletMode: true,
      // allowEditPrice: true,
    });
  };
})();
  </script>
</body>
</html>
