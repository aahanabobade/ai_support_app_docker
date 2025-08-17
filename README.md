### AI-Powered Customer Support Interface (Dockerized)
---
This repository contains the Dockerized version of the AI-powered customer support interface. It allows running the Django application inside a container for easier deployment and environment management.

---
### Features 
1. Run the Django app in a Docker container.
2. Preconfigured dependencies via requirements.txt.
3. Easy setup without installing Python or other libraries locally.
4. Supports existing database migrations and superuser creation.
---
### Prerequisites
Docker installed on your system.

---
### Setup Instruction
1. Clone the Repository
```bash
git clone https://github.com/aahanabobade/ai_support_app_docker.git
cd ai_support_app_docker
```
2. Build the Docker Image
```bash
docker build -t ai_support_app .
```
3. Create a Docker Volume for Database Persistence
```bash
docker volume create ai_support_db
```
This will start the Django development server inside the container, accessible at http://127.0.0.1:8000.

4. Applying Migrations
If needed, you can apply migrations inside the container:
```bash
docker exec -it <container_id> python manage.py migrate
```
5. Creating a Superuser
To create a Django admin superuser inside the container:
```bash
docker exec -it <container_id> python manage.py createsuperuser
```


### Assumptions

1. User Roles: Customers and Admins are clearly separated; admin accounts are created in Django admin.
2. AI Responses: Google Gemini AI is used to generate responses; accuracy depends on the AI model.
3. Security: CSRF protection and user authentication are enforced.
4. Environment Variables: Gemini API key must be exported locally before running the server.
5. No Real-time Notifications: The system is not integrated with SMS/email alerts for ticket updates.

### Limitations

1. Single Machine Testing: The system is tested locally; production deployment may require Docker, a web server, and proper environment variable management.
2. AI Reliability: AI responses might occasionally require manual correction.
3. No Multi-language Support: Currently supports only English.
4. Basic UI/UX: Focus is on functionality rather than advanced design.
5. Admin Panel Role Check: Admin cannot act as customer, but the interface is basic and could be enhanced with detailed role validation messages.

### Tech Stack

1. Single Machine Testing: The system is tested locally; production deployment may require Docker, a web server, and proper environment variable management.
2. AI Reliability: AI responses might occasionally require manual correction.
3. No Multi-language Support: Currently supports only English.
4. Basic UI/UX: Focus is on functionality rather than advanced design.
5. Admin Panel Role Check: Admin cannot act as customer, but the interface is basic and could be enhanced with detailed role validation messages.

### How to use

1. Register as a new customer or log in as an existing one.
2. Customers can create tickets with messages describing their issues.
3. Admins can:
    a. View all tickets.
    b. Manually respond to tickets
    c. Auto-generate responses via AI
    d. Re-generate AI responses if needed
4. Customers can view replies and ticket status.

### Contact/Support
This project is maintained by Aahana Bobade. For any issues or questions regarding setup or usage, please contact via GitHub or email(aahanabobade@gmail.com).
