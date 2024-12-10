html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Execute Function on Button Click</title>
</head>
<body>
  <button id="executeButton">Click Me</button>

  <script>
    const HPP_API_URL = `${window.location.origin}/${BPSystem?.organization}/hostedPayments/1.0`;

    const getHppSecurityToken = async () => {
      const requestUrl = `${HPP_API_URL}/authenticate-session`;

      return fetch(requestUrl, {
        headers: { 'Content-Type': 'application/json', sessionid: BPSystem.sessionId },
        method: 'POST',
        body: JSON.stringify({
          sessionId: BPSystem.sessionId,
        }),
      })
        .then(response => response.json())
        .then(response => response?.accessToken?.content)
        .catch(() => undefined);
    };

    document.getElementById('executeButton').addEventListener('click', async function() {
      const securityToken = //'eyJhbGciOiJSUzI1NiJ9.eyJ0eXBlIjoiVVNFUiIsIm9yZ05hbWUiOiJub29ubGlnaHRfZGV2IiwiZW52aXJvbm1lbnRJZCI6IjA5NjYwMmFhLWEwMzMtNGRhZC04MTVkLTc1NDEwNWRiZjZmYyIsImlkZW50aXR5IjoiNDNERjExMkY5ODQxQkMxRjQxM0YiLCJzZXNzaW9uSWQiOiJQZlBXdXh4Uk1yU1hhdFN2SmJCUk5nbFVaRVBNd0xJRWRGc0xlUExzIiwidXNlcklkIjoiMTU2MDY5IiwidXNlcm5hbWUiOiJicC5hcGkudXNlciIsInR0bCI6MTUsInRva2VuVHlwZSI6IkFDQ0VTUyIsImlhdCI6MTczMzg1OTM2NSwiZXhwIjoxNzMzODYwMjY1fQ.lLmFtbvNocc0AMmROnNVJ4g0uV0AXTTh12kqdcN8_UJvRge8d7IYCRKeM16KVuPwk0XsF1vVXefYKlBTNO1lFESbyqQEXtoeZ2627tZpocB8yiHExJpdrAjmB4iNuIP9yGD3o06Q08oTbLeirI6WvEXVFZj1XHH73EyXfvFA5B8TH-pR-YAxkqVfXAk1isH7rut4xl-Szaf4Uft83bYnD8I1uursisGCNaRrav6yhpP84XRJS2PVf1jcRLd7weDjtgafowizZo4dGOc5WcM59dau3CmpBNAseuIOu42GQrUB2-euMCkLFJeSs3cov55-kKnXyqXZoAwCQ0XP3-aJpQ';
      await getHppSecurityToken();
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
          apiUrl: "https://sandbox.billingplatform.com/noonlight_dev/hostedPayments/1.0/",
          securityToken: securityToken,
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
