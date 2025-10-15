# Visual Product Matcher

This is the main repository that contains both the frontend and backend as submodules.

## Project Structure

```
Visual-Product-Matcher-Main/
├── backend/          # Backend API (Python/Flask)
├── frontend/         # Frontend Application (React/Next.js)
└── README.md
```

## Getting Started

### Clone the Repository with Submodules

To clone this repository along with all submodules, use:

```bash
git clone --recurse-submodules https://github.com/isatyamshivam/Visual-Product-Matcher-Main.git
```

Or if you've already cloned the repository without submodules:

```bash
git submodule update --init --recursive
```

### Update Submodules

To pull the latest changes from all submodules:

```bash
git submodule update --remote --merge
```

## Submodules

- **Backend**: [visual_product_matcher](https://github.com/isatyamshivam/visual_product_matcher)
- **Frontend**: [Visual-Product-Matcher-Frontend](https://github.com/isatyamshivam/Visual-Product-Matcher-Frontend.git)

## Setup Instructions

### Backend Setup

```bash
cd backend
# Follow the backend README for setup instructions
```

### Frontend Setup

```bash
cd frontend
# Follow the frontend README for setup instructions
```

## Development

For detailed setup and development instructions, please refer to the README files in each submodule:
- Backend: `backend/README.md`
- Frontend: `frontend/README.md`

## License

See individual submodule repositories for license information.
