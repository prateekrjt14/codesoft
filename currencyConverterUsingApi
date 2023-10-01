import org.json.JSONObject;
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.URL;
import java.util.Scanner;

public class currencyConverter {
    public static void main(String[] args) throws IOException {
        Scanner sc = new Scanner(System.in);

        System.out.print("Enter the base currency (for eg 'INR', 'USD',...etc): ");
        String base = sc.nextLine().toUpperCase();

        System.out.print("Enter the target currency : ");
        String target = sc.nextLine().toUpperCase();

        System.out.print("Enter the amount to convert: ");
        double amount = sc.nextDouble();

        sendExchangeRateRequest(base, target, amount);
    }
    private static void sendExchangeRateRequest(String base, String target, double amount) throws IOException {
       String request_url = "http://api.exchangerate.host/convert?access_key=66b9284badd1c914abdef9272f00325c&from="+base+"&to="+target+"&amount="+amount;
       URL url = new URL(request_url);
        HttpURLConnection httpURLConnection = (HttpURLConnection) url.openConnection();
        httpURLConnection.setRequestMethod("GET");
        int responseCode = httpURLConnection.getResponseCode();

        if(HttpURLConnection.HTTP_OK == responseCode)
        {
            BufferedReader in = new BufferedReader(new InputStreamReader(httpURLConnection.getInputStream()));
            String inputLine;
            StringBuffer response = new StringBuffer();

            while((inputLine = in.readLine()) != null)
            {
                response.append(inputLine);
            }in.close();

            JSONObject obj = new JSONObject(response.toString());
            if (obj.has("result"))
            {
                double convertedAmount = obj.getDouble("result");
                System.out.println("\n" + amount + " " + base + " = " + convertedAmount + " " + target);
            }
            else
            {
                System.out.println("Invalid response format. 'result' field not found as expected.");
            }
        }

        else
        {
            System.out.println("GET request failed");
        }
    }
}
