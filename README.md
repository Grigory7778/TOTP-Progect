markdown

# TOTP Generator and Validator

This project provides a simple implementation of a Time-based One-Time Password (TOTP) generator and validator in Java. It uses the HMAC-SHA1 algorithm to generate TOTPs based on a shared secret key and the current time.

## Project Structure

- **com.example.TOTP**: The main class that includes methods for generating and validating TOTPs.
- **TOTPTest**: A test class to verify the functionality of the TOTP generation and validation methods.

## Usage

### Generating a TOTP

To generate a TOTP based on the current time, you can use the `generateCurrentTOTP` method:

```java
String totp = TOTP.generateCurrentTOTP();
System.out.println("Current TOTP: " + totp);

Validating a TOTP

To validate a TOTP, use the validateTOTP method with the TOTP, the current time, and the secret key:

java

long timestamp = System.currentTimeMillis();
long counter = timestamp / 1000 / TOTP.PERIOD;
String otp = TOTP.generateTOTP(counter);

boolean isValid = TOTP.validateTOTP(otp, counter);
System.out.println("Is valid: " + isValid);

Running Tests

You can run the provided test to ensure that the TOTP generation and validation works correctly. The test is written using TestNG:

java

import static org.junit.jupiter.api.Assertions.assertTrue;

import com.example.TOTP;
import org.testng.annotations.Test;

public class TOTPTest {

    @Test
    public void testValidTOTPGeneration() {
        long timestamp = System.currentTimeMillis();
        long counter = timestamp / 1000 / TOTP.PERIOD;
        String otp = TOTP.generateTOTP(counter);

        // Validate the TOTP
        assertTrue(TOTP.validateTOTP(otp, counter));
    }
}

Building the Project

To build the project, you can use any Java IDE (e.g., IntelliJ IDEA, Eclipse) or build tools like Maven or Gradle. Make sure to include the necessary dependencies for JUnit and TestNG if you want to run the tests.
Dependencies

    Java SE 8 or higher
    TestNG for testing

License

This project is licensed under the MIT License. See the LICENSE file for details.
Acknowledgements

This implementation is inspired by the RFC 6238 specification for TOTP: Time-Based One-Time Password Algorithm.

markdown


### Explanation of Changes:
- Fixed the code block formatting for better readability.
- Added missing code block delimiters.
- Ensured section headers are correctly formatted.
- Corrected minor grammar issues.


