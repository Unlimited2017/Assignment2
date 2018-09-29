# Assignment2
1)The first function of assignment
 # In IDLE, press F5, then inputing "addBinary('1101', '100')", Enter to run
 
def addBinary(x, y):
   
        max_len = max(len(x), len(y)) 
  
        x = x.zfill(max_len) 
        y = y.zfill(max_len) 
          
        # initialize the result 
        result = '' 
          
        # initialize the carry 
        carry = 0
  
        # Traverse the string 
        for i in range(max_len - 1, -1, -1): 
            r = carry 
            r += 1 if x[i] == '1' else 0
            r += 1 if y[i] == '1' else 0
            result = ('1' if r % 2 == 1 else '0') + result 
            carry = 0 if r < 2 else 1     # Compute the carry. 
          
        if carry !=0 : result = '1' + result 
  
        return result.zfill(max_len) 
 
 2)The second function of the assignment2
 
  #In IDLE, press F5, then inputting plusOne([1, 2, 3]), press enter to run
  
def plusOne(digits):
      
        plus = 1
        for i in range(len(digits)-1, -1, -1):
            if digits[i] + plus > 9:
                digits[i] = 0
                plus = 1
            else:
                digits[i] = digits[i] + plus
                plus = 0
        if plus == 1:
            digits.insert(0, 1)
            
        return digits 



  3)  The third function of the assignment2
# in IDLE, press F5, and then inputing "roman_to_integers('V')", press enter to run  

def roman_to_integers(roman_string):
       
        num_tuple = [1000, 500, 100, 50, 10, 5, 1]
        roman_tuple = ['M', 'D', 'C', 'L', 'X', 'V', 'I']
        
        merge_dic = dict(zip(roman_tuple, num_tuple))
        
        integer = 0
        
        for i in range(len(roman_string)-1):
           
            if merge_dic[roman_string[i]] < merge_dic[roman_string[i+1]]:
                integer -= merge_dic[roman_string[i]]
           
            else:
                integer += merge_dic[roman_string[i]]
        
        integer += merge_dic[roman_string[-1]]
        return integer
