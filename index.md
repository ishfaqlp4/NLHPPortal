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
  script.src = "https://cdn.aws.billingplatform.com/hosted-payments-ui@release/lib.js";

  document.body.append(script);
  script.onload = function () {
    HostedPayments.renderPaymentForm({
      /** Required parameters: */
     apiUrl: "https://sandbox.billingplatform.com/noonlight_dev/hostedPayments/1.0/",
      securityToken: "eyJhbGciOiJIUzUxMiJ9.eyJlbnZpcm9ubWVudElkIjoiMDk2NjAyYWEtYTAzMy00ZGFkLTgxNWQtNzU0MTA1ZGJmNmZjIiwiY2xpZW50SWQiOiJ1dGtLS2Q4VEQyN05xcFY5OGJtWVloYzhXNlI0YkJ1NiIsInJvbGVzIjpbIkFETUlOIl0sIlRva2VuVHlwZSI6IkFDQ0VTUyIsImlhdCI6MTczNDU1NzUxOSwiZXhwIjoxNzM0NjQwMzE5fQ.jP_naLx8waigIUOwumsrWdaEsYb-YXfUDsaMW43Yqcwai8cQ2U3xOODs8hFIt__ILfCKfq32nnskLgy_k6RuvQ",
      refresh_token:"eyJhbGciOiJIUzUxMiJ9.eyJlbnZpcm9ubWVudElkIjoiMDk2NjAyYWEtYTAzMy00ZGFkLTgxNWQtNzU0MTA1ZGJmNmZjIiwiY2xpZW50SWQiOiJ1dGtLS2Q4VEQyN05xcFY5OGJtWVloYzhXNlI0YkJ1NiIsInJvbGVzIjpbIkFETUlOIl0sIlRva2VuVHlwZSI6IlJFRlJFU0giLCJpYXQiOjE3MzQ1NTc1MTksImV4cCI6MTczNDY0MDMxOX0.P8u3La7iT1tTaksqS7hOWr1UmPDujzoudgr3Pi6eJ7gZm9Ic6UEx-h_2hW2eG0RQ56uXYNP2OJCrzQ0AUbAAAA",
      
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
