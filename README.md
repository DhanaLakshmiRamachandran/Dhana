import java.util.Scanner;

public class PrimeNumbersSum {
	public static int output1;

	public static void main(String[] args) {
		NumberOfPrime(14);
		System.out.println(output1);
	}

	public static void NumberOfPrime(int input1) {
		int[] prime = new int[25];
		int k = 0;
		int flag;
		for (int i = 10; i <= 99; i++) {
			flag = 0;
			for (int j = 2; j <= i / 2; j++) {
				if (i % j == 0) {
					flag = 1;
				}
			}
			if (flag == 0) {
				prime[k] = i;
				k++;
			}
		}
		int len = k;
		flag = 0;
		for (int i = 0; i < len; i++) {
			if (input1 == prime[i]) {
				flag = 1;
				output1 = 1;
				break;
			}
		}
		if (flag != 1) {
			for (int i = 0; i < len; i++) {
				if (input1 % prime[i] == 0) {
					output1 = input1 / prime[i];
					flag = 1;
					break;
				}
			}
		}
		int index = -1;
		if (flag != 1) {
			for (int i = 0; i < len; i++) {
				int num = input1 % prime[i];
				for (int j = 0; j < len; j++) {
					if (prime[j] == num) {
						flag = 1;
						index = j;
						break;
					}
				}
				if (index > -1) {
					break;
				}
			}
			if (flag == 1) {
				output1 = (input1 / prime[index]) ;
			} else {
				output1 = 0;
			}
		} else {

		}
	}
}
