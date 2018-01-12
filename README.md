import java.util.Scanner;

public class Comparison {

	public static void main(String[] args) {
		Scanner scnr = new Scanner(System.in);

		int userNum1 = 0;
		int userNum2 = 0;
		int digits1 = 0;
		int digits2 = -1;
		int i;
		String numString1;
		String numString2;
		

		while (digits1 != digits2) {

			System.out.println("Please enter a number: ");
			userNum1 = scnr.nextInt();
			System.out.println("Please enter another number that has the same number of digits: ");
			userNum2 = scnr.nextInt();

			// Convert to value of String length and compare i.e. # of digits

			digits1 = String.valueOf(userNum1).length();
			digits2 = String.valueOf(userNum2).length();

			if (digits1 != digits2) {
				System.out.println("Those numbers don't have the same number of digits...\nTry again.\n");

			}

		}
		
		// Convert to String to be able to use charAt to locate digits
		
		numString1 = String.valueOf(userNum1);
		numString2 = String.valueOf(userNum2);
		int matchNum = 0;
		int storeNum = 0;
		
		// Main code - add numeric values of digits and compare totals
		
		for (i = 0; i < digits1; ++i) {
			char firstNum = numString1.charAt(i);
			int j = Character.getNumericValue(firstNum);
			char secondNum = numString2.charAt(i);
			int k = Character.getNumericValue(secondNum);
			
			matchNum = j + k;
			if (i <= 0) {
				storeNum = matchNum;	
			}
			if (storeNum != matchNum) {
				break;
			}
			
			// Print result
				
		}
		if (storeNum == matchNum) {
			System.out.println("True");
		}
		else {
			System.out.println("False");
		}
        scnr.close();
	}

}

