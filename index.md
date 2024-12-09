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
      script.src = "https://cdn.aws.billingplatform.com/hosted-payments-ui@release/lib.js";
      document.body.append(script);
      script.onload = function () {
        HostedPayments.renderPaymentForm({
          /** Required parameters: */
          targetSelector: 'body',
          amount: 100,
          environmentId: '096602aa-a033-4dad-815d-754105dbf6fc',
          billingProfileId: '1ba91f19-61f9-1c28-e063-ee043c0a3abe',
          paymentGateways: ['Adyen_CC', 'Adyen_DD'],
          /** Additional parameters: */
          walletMode: true,
          allowEditPrice: true,
          fullName: 'John',
          state: 'CO'
        });
      };
    });
  </script>
</body>
</html>
