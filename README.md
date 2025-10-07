# textcalc
just a bootcamp results of what have I learned







def text_based_calculator():
    print("hello and welcome to text calculator!")
    print("available operations: +, -, *, /, ** (power), % (ramainder of division)")
    print("to leave write 'exit'")
    
    while True:
        try:
            user_input = input("\nenter an expression (for example: 5 + 3): ").strip()
            
            if user_input.lower() == 'exit':
                print("thank u for using the calculator!")
                break
            
            parts = user_input.split()
            
            if len(parts) != 3:
                print("error: enter expression in format 'operator number number'")
                continue
            
            num1 = float(parts[0])
            operator = parts[1]
            num2 = float(parts[2])
            
            result = None
            
            if operator == '+':
                result = num1 + num2
            elif operator == '-':
                result = num1 - num2
            elif operator == '*':
                result = num1 * num2
            elif operator == '/':
                if num2 == 0:
                    print("error: division by zero!")
                    continue
                result = num1 / num2
            elif operator == '**':
                result = num1 ** num2
            elif operator == '%':
                if num2 == 0:
                    print("error: division by zero!")
                    continue
                result = num1 % num2
            else:
                print(f"error: unknown operator '{operator}'")
                continue
            
            print(f"result: {num1} {operator} {num2} = {result}")
            
        except ValueError:
            print("error: please, write numbers correctly")
        except Exception as e:
            print(f"error occured: {e}")

if __name__ == "__main__":
    text_based_calculator()
