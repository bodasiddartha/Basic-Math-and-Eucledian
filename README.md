# Basic-Math-and-Eucledian

Basic Maths Concept


1)
Extraction of digits: Take the modulo (%) of 10 for an number.

N=7789
1) 7789%10 -> `9`
2) divide n by 10 that becomes 778.
3) again take modulo of 10 for n(778) -> 778%10 -> `8`
4) divide n by 10 that becomes 77
5) again take modulo of 10 for n(77) -> 77%10 -> `7`
6) divide n by 10 that becomes 7
7) again take modulo of 10 for n(7) -> 7%10 -> `7`
8) divide b by 10 that becomes 0 (7/10) -> here we stop and extracted all the digits.

   `void printDigits(int n){
      while(n>0){
        int t=n%10;
        System.out.println(t);
        n/=10;
     }
   }`


   `int noofdigits = (int) Math.log10(n)+1;`

   log10(n) -> log to the base 10 of n -> this answers Qn `At what power 10 must be raised to become n`

   TC: O(log10(N)) -> how many times the loop will run (how many times number can be divisible by 10) ?? log10(N) times.

   when ever your loop is based on division (suppose if you are dividing by 2 your TC will be O(log2(n)) TC will be in terms of log.








2) Armstrong number: If the sum of, digits raised to the power of no of digits in that number == number ->its a Armstrong number.


123 -> 1cube + 2cube + 3cube must be equal to 123 -> then 123 is an Armstrong number -> why cube? because it has 3 digits
1234 -> 1power4 + 2power4+ 3power4 + 4power4 must be equal to 1234 -> then 1234 is an Armstrong number -> why power 4? because it has 4 digits.

`public static void main(String[] args) {
		// Write your code here
		Scanner x=new Scanner(System.in);
		int n=x.nextInt();
		int t1=n;
		int new1=0;
		int nOfDigits=(int)Math.log10(n)+1;
		while(n>0){
			int t=n%10;
			n/=10;
			new1+=Math.pow(t, nOfDigits);
		}
		if((int)new1 == t1) System.out.println(true);
		else System.out.println(false);
	}`



Printing all the Divisors of a number:

public static int sumOfAllDivisors1(int n){
        
        int c=0;
      
        for(int i=1;i*i<=n;i++){
            if(n%i==0) {
                c+=i; 
                if(n/i!=i) {c+=(n/i);}
            }
        }
       
        return c;
    }



Prime number check:
What's a prime number? A number that exactly have 2 numbers, 1 and iteself

Bruteforce:

boolean checkPrime(int N){
int c=0;
for(int i=1;i<=n;i++){
	if(N%i==0) c++;
}
if(c==2) return true;
else return false;
}



TC -> O(N)



Optimized:

boolean checkPrime(int N){
	int c=0;
 	for(int i=1;i*i<=N;i++){
		if(N%i==0) c++;
  		if(N/i!=i) c++;
  	}
   if(c==2) return true;
   else return false;
}




GCD or HCF (Greatest Common Divisor or Highest Common Factor)

N1 = 9 N2=12

factors of 9 -> 1, 3, 9
factors of 12 -> 1, 2, 3, 4, 6, 12

so common factors are 1, 3 -> highest is 3 so GCD of 9 and 12 is 3


GCD of 11, 13 is 1 -> (11 has 1, 11 as factors and 13 has 1, 13 as factors)


1st form:

gcd=1;
for(int i=1;i<=min(n1, n2);i++){
	if(n1%i==0 && n2%i==0) gcd=i;
}
//at the end highest common factor will be the answer.

TC -> O(min(n1, n2))
another way.

//if n1 =20, n2 =40 we can follow below its basically searching from highest to lowest and if we find answer we are breaking it, anyhow, its TC will be same as above

for(int i=min(n1,n2);i>=1;i++){
	if(n1%i==0 && n2%i==0) {
 	gcd=i;
  	break;
   	}
}


TC -> O(min(n1, n2))




`EUCLIDEAN ALGORITHM`

Euclidean algorithm states that `gcd(a,b)=gcd(a-b,b) where a>b`





















 


