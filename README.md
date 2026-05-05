public class Problem_One {
    public static void main(String[] args) {
        String s = "abca";
        int n = s.length();
        int maxSum = 0;

        String doubled = s + s; //doubled it so we can check cycle cases...

       
        for (int i = 0; i < n; i++) {
            boolean[] seen = new boolean[26];// boolean array where we store true value if seen ...
            int sum = 0;

            // Inner loop (expand substring from index i)
            for (int j = i; j < i + n; j++) {
                char ch = doubled.charAt(j);

                
                if (seen[ch - 'a']) {
                    break;
                }
                
                seen[ch - 'a'] = true;
                sum += (ch - 'a' + 1);
                maxSum = Math.max(maxSum, sum);
            }
        }

        System.out.println(maxSum);
    }
}
