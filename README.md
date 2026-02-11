# VShare Frontend

> A platform for sharing your stories through voice. Record your thoughts, experiences, and tales, and share them with friends.

## ✨ Features

- **Voice Recording:** Easily record audio clips directly in the browser.
- **Story Sharing:** Share your recorded stories with your friends.
- **Friend System:** Add and manage your friends to control who hears your stories.
- **Personal Dashboard:** A central place to listen to stories shared by your friends.
- **User Authentication:** Secure login and registration.

## 🚀 Tech Stack

- **Frontend:** [React](https://reactjs.org/) with [Vite](https://vitejs.dev/)
- **Deployment:** AWS S3 & CloudFront with GitHub Actions for CI/CD.

## 📂 Project Structure

The project follows a feature-sliced design to keep the codebase organized and scalable.

```
src/
├── assets/          # Static files (images, svg, global CSS)
├── components/      # Global UI components (Button.jsx, Modal.jsx)
├── config/          # Constants, API keys, and global config
├── features/        # Business logic organized by feature
│   ├── auth/
│   │   ├── api/        # Fetch calls (authApi.js)
│   │   ├── components/ # Private components (LoginForm.jsx)
│   │   ├── hooks/      # Feature-specific hooks (useAuth.js)
│   │   └── index.js    # Public entry point for the feature
│   └── dashboard/
├── hooks/           # Shared hooks (useWindowSize.js, useForm.js)
├── layouts/         # Page wrappers (AuthLayout.jsx, DashboardLayout.jsx)
├── lib/             # Third-party library setups (axios.js, firebase.js)
├── routes/          # Route definitions (AppRoutes.jsx)
├── store/           # Global state (Zustand or Redux slices)
├── utils/           # Helper functions (formatDate.js)
├── App.jsx          # Main application component
└── main.jsx         # React DOM rendering entry point
```

## 🛠️ Getting Started

Follow these instructions to get a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

- Node.js (Version 20 or higher, as per `.github/workflows/deploy.yml`)
- npm

### Installation

1.  **Clone the repository**

    ```sh
    git clone https://github.com/your-username/vshare-frontend.git
    cd vshare-frontend
    ```

2.  **Install dependencies**

    ```sh
    npm install
    ```

3.  **Set up environment variables**
    Create a `.env.local` file in the root of the project and add the necessary environment variables (e.g., API endpoints, service keys).

4.  **Run the development server**
    ```sh
    npm run dev
    ```

## 📦 Build & Deployment

- **To create a production build:**

  ```sh
  npm run build
  ```

- **Deployment:**
  The project is configured for continuous deployment using GitHub Actions. Pushing to the `main` branch will automatically trigger a workflow that builds the project, deploys the static files to an AWS S3 bucket, and invalidates the AWS CloudFront cache.
