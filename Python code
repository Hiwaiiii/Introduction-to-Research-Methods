import re

def count_pronouns(file_path):
    # Define lists of personal and possessive pronouns
    personal_pronouns = ["I", "you", "he", "she", "it", "we", "they", "me", "him", "her", "us", "them"]
    possessive_pronouns = ["my", "your", "his", "her", "its", "our", "their", "mine", "yours", "hers", "ours", "theirs"]
    try:
        with open(file_path, 'r') as file:
            text = file.read().lower()

            # Count occurrences of personal and possessive pronouns and dialogues
            personal_count = sum(1 for word in text.split() if word in [p.lower() for p in personal_pronouns])
            possessive_count = sum(1 for word in text.split() if word in [p.lower() for p in possessive_pronouns])
            
            # Count dialogues
            dialogue_count = len(re.findall(r'"', text)) / 2

            return personal_count, possessive_count, dialogue_count

    except FileNotFoundError:
        print(f"File not found: {file_path}")
        return None

# Example usage:
file_path = 'aroom_updated.txt'  # replace with your file path
result = count_pronouns(file_path)

if result:
    personal_count, possessive_count, dialogue_count = result
    print(f"Personal pronouns: {personal_count}")
    print(f"Possessive pronouns: {possessive_count}")
    print(f"dialogue: {dialogue_count}")
