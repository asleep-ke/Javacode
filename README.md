leetcode第22题，生成有效括号
public List<String> generateParenthesis(int n) {
 List<String> res=new ArrayList<>();
        if(n==0) return res;
        deepsearch("",n,n,res);
        return res;
    }
    //n表示剩余左括号的个数，m表示剩余右括号的个数，curs表示生成的括号，res表示返回的结果
    //使用递归，表示所有可能的情况。主要分为以下几种情况1：当剩余的左括号‘（’的数量小于剩余有括号的数量时，可以认为右括号的前面没有左括号，这时就没必要继续，剪枝
    //直接返回，2.当不满足1的条件时，就可以继续往下遍历，n减1，就让curs加上一个左括号，同理m减1，就让curs加上一个右括号
    public static void deepsearch(String curS,int n,int m,List<String> res){
        if(n==0&&m==0){//写递归的第一步，写出递归结束的条件
           res.add(curS);
            return;
        }
        if(n>m){
            return;
        }
        if(n>0){
            deepsearch(curS+"(",n-1,m,res);
        }
        if(m>0){
            deepsearch(curS+")",n,m-1,res);
        }
        }
  
