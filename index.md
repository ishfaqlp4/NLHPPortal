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
      securityToken: "eyJhbGciOiJSUzI1NiJ9.eyJ0eXBlIjoiVVNFUiIsIm9yZ05hbWUiOiJub29ubGlnaHRfZGV2IiwiZW52aXJvbm1lbnRJZCI6IjA5NjYwMmFhLWEwMzMtNGRhZC04MTVkLTc1NDEwNWRiZjZmYyIsImlkZW50aXR5IjoiNDNERjExMkY5ODQxQkMxRjQxM0YiLCJzZXNzaW9uSWQiOiJQZlBXdXh4Uk1yU1hhdFN2SmJCUk5nbFVaRVBNd0xJRWRGc0xlUExzIiwidXNlcklkIjoiMTU2MDY5IiwidXNlcm5hbWUiOiJicC5hcGkudXNlciIsInR0bCI6MTUsInRva2VuVHlwZSI6IkFDQ0VTUyIsImlhdCI6MTczMzg2MDM5MywiZXhwIjoxNzMzODYxMjkzfQ.dULJd8rJGmEARxs9bZBjOlheqARlR008ucQhwcv4Z38iq4ppSJBPxpObcjjuPyNaNppd1_RzuSMdmwHSR8CC4WoNktpT7zNvSijLBAzf_nc28M332zMj7WCG4xbc74PMDxD0lzPd4ZWGefpZnoIaRj1LDU86j32YJHbkjAFolxBB2B16WlqYnLQl8lFJr6gU1tTWpM4a40pvG3dxD0pKawg5t-36atZGi1nLuzkBCZVT7eJdXryZcZDlG8_BEMmRsDdXV_Mv8vkJK0eL6thWHqjtGIKplPNck0P748u8x5IyETnQIgH1nR3xHA0i6eq_ZQb1i8RZrZm01rW7CsRSiw","refresh_token":"eyJhbGciOiJSUzI1NiJ9.eyJ0eXBlIjoiVVNFUiIsIm9yZ05hbWUiOiJub29ubGlnaHRfZGV2IiwiZW52aXJvbm1lbnRJZCI6IjA5NjYwMmFhLWEwMzMtNGRhZC04MTVkLTc1NDEwNWRiZjZmYyIsImlkZW50aXR5IjoiNDNERjExMkY5ODQxQkMxRjQxM0YiLCJzZXNzaW9uSWQiOiJQZlBXdXh4Uk1yU1hhdFN2SmJCUk5nbFVaRVBNd0xJRWRGc0xlUExzIiwidXNlcklkIjoiMTU2MDY5IiwidXNlcm5hbWUiOiJicC5hcGkudXNlciIsInR0bCI6MTUsInRva2VuVHlwZSI6IlJFRlJFU0giLCJpYXQiOjE3MzM4NjAzOTMsImV4cCI6MTczMzk0MzE5M30.tN2O3JY_WW0glVdaMCfFsXBob__xcD6LSqgg1D5FVAITLSN8JYeg59aq-GlZ13dhTWgQ7sNhji1lWjEA25_-bg33uzXc4Ky5Cno_zCA-BQyhFCiilSwJ3TzB0QK4zJaui8MD-39o4xEcLV6bixnMwZuBqzzUXs5QtP2i-fQwtgHgbC84HU6gi-ZHFqkKElcjY3cLNXcxS8XyYdv1--rNWSPCGVjpKNHqaDHmTXZmwZQdWg3ySYSk-vvEL29UicLdGYhFXZTWvNl7NuyI1RK5E1fnPHEc5N6SMr4ebg_R6niC_FAkOUr61JFfVJkuPAf6uHQYIOdsIRqql4_VmHqu8Q",
      
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
