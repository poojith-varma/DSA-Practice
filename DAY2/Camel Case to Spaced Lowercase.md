Problem Statement:



Code:

``` java

class Solution {
    public String convertCamelCase(String cstr) {
        
        StringBuilder sb = new StringBuilder();
        
        for(int i=0; i<cstr.length(); i++ ){
            char ch = cstr.charAt(i);
            if(Character.isUpperCase(ch)){
                if(i!=0){
                    sb.append(' ');
                }
                sb.append(Character.toLowerCase(ch));
            }

            else{
                sb.append(ch);
            }
        }

        return sb.toString();
    }
}


```
