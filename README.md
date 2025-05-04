# password-generate
import random
import string

def generate_paassword(length, complexity):
  if complexity  == 'low':
    characters = string.ascii_lowercase
  elif complexity == 'medium':
    characters = string.ascii_letter +string.digits
  elif complexity == 'high':
    characters = string.ascii_letters + string.digits + string.punctuation
  else:
    raise ValueError("Invalid complexity level.choose from 'low', 'medium', or 'high'.")
  password = ''.join(random.choice(characters) for _ in range(length))
  return password

def main():
print("Welcome to the python Password Generator!")
while True:
  try:
    length = int(input("Enter the desired password integer for length."))
    if length <= 0:
      print("Please enter a positive integer for length.")
      continue
    break
  except ValueError:
    print("Invalid input. Please enter a number.")
use_uppercase = input("Include uppercase letters? (y/n):").strip().lower() =='y'
use_digits = input("Include digits? (y/n): ").strip().lower() == 'y'
use_special = input("Include special characters? (y/n): ").strip().lower() == 'y'
try:
  password = generate_password(length, use_uppercase,use_digits, use_special)
  print("/nGenerated Password:", password)
  except ValueErrorr as e:
  print(e)
if __name__ == "__main__":
  main()
    
