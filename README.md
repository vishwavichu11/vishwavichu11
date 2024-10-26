!pip install openai
import openai

# Set up your OpenAI API key
openai.api_key = 'sk-_gk8sNCzw3Rs1J0hm2cfK4J1FCCCT0W7YdEXs7Lta8T3BlbkFJlpnVqml3gyoBhjc-U4K7_y7K0J9GkrUL31yF9QzdoA'

def get_response(prompt):
    response = openai.ChatCompletion.create(
        model="gpt-3.5-turbo",
        messages=[{"role": "user", "content": prompt}]
    )
    return response.choices[0].message['content']

def study_buddy():
    print("Welcome to your virtual study buddy! Type 'exit' to end the session.")
    
    while True:
        user_input = input("You: ")
        
        if user_input.lower() == 'exit':
            print("Goodbye! Happy studying!")
            break
        
        # Get a response from the GPT model
        response = get_response(user_input)
        print(f"Study Buddy: {response}")

if __name__ == "__main__":
    study_buddy()

