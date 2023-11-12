# AutoReadMeGen
This script prompts you to enter the project name, description, and installation steps.
# automate_readme.py

def generate_readme(project_name, description, installation_steps):
    """
    Generate a README.md file for a GitHub repository.

    Args:
    - project_name (str): The name of the project.
    - description (str): A brief description of the project.
    - installation_steps (list): A list of installation steps.

    Returns:
    - str: The content of the README.md file.
    """
    readme_content = f"# {project_name}\n\n{description}\n\n## Installation\n"
    
    for step_number, step in enumerate(installation_steps, start=1):
        readme_content += f"{step_number}. {step}\n"
    
    return readme_content

def save_readme(content, filename="README.md"):
    """
    Save the README content to a file.

    Args:
    - content (str): The content to be saved.
    - filename (str): The name of the file. Default is "README.md".
    """
    with open(filename, "w") as file:
        file.write(content)

if __name__ == "__main__":
    # Input values
    project_name = input("Enter the name of your project: ")
    description = input("Provide a brief description of your project: ")
    
    installation_steps = []
    while True:
        step = input("Enter an installation step (or type 'done' to finish): ")
        if step.lower() == "done":
            break
        installation_steps.append(step)

    # Generate README content
    readme_content = generate_readme(project_name, description, installation_steps)

    # Save README to file
    save_readme(readme_content)

    print("README.md generated successfully!")
