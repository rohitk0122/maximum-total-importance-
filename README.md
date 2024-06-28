# maximum-total-importance-
class Solution {
    public long maximumImportance(int n, int[][] roads) {
        long ans = 0;
        long[] count = new long[n];

        for (int[] road : roads) {
            int u = road[0];
            int v = road[1];
            count[u]++;
            count[v]++;
        }

        Arrays.sort(count);

        for (int i = 0; i < n; ++i)
            ans += (i + 1) * count[i];

        return ans;
    }

    public static void main(String[] args) {
        Solution sol = new Solution();
        int n = 5;
        int[][] roads = {{0, 1}, {1, 2}, {2, 3}, {3, 4}, {0, 2}};
        System.out.println(sol.maximumImportance(n, roads)); // Example usage

    }
}
