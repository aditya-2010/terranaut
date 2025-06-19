# Terranaut — Your co-pilot for managing infrastructure as code
---
## A CLI wrapper for Terraform that simplifies multi-environment infrastructure management

### What is Terranaut?
**Terranaut** is a productivity tool for DevOps teams managing Terraform across multiple environments (dev/staging/prod). It provides:

**🔒 Environment Isolation**
- Dedicated directories per environment

- Auto-switching between configurations

- No accidental prod deployments

**🛡️ Safety Guardrails**

- Interactive confirmation for destructive operations

- Environment-aware command execution

- Prod protection by default

**♻️ DRY Infrastructure Code**

- Central shared modules directory

- Environment-specific variables injection

- Reduced configuration duplication

### Why use Terranaut?
Traditional Terraform workflows become error-prone when managing many environments. This tool solves:

✅ Cognitive overload - Focus on one environment at a time \
✅ Statefile confusion - Auto-configured backend isolation \
✅ Secret leakage risk - Never see prod variables in dev \
✅ Onboarding friction - Standardized team workflows

### Key Features
- **Environment management:** create, list, switch environments

- **Terraform proxy:** All standard commands (plan, apply, etc.)

- **Smart defaults:** Auto-configured backend paths

- **Safety checks:** Prod destruction confirmation

- **Shared modules:** Central reusable components

<!-- - **Environment Switching:** Easily switch between dev/staging/prod with `terranaut switch prod` – Sets backend config, variables, and state for the target env.
- **Safe Workflow Guardrails:**	Auto-block destroy in prod without a `--force` flag or 2FA confirmation.
- **State management:**	Auto-configure remote backends (e.g., S3 + DynamoDB for locking).
- **Secret Management:**	Integrate with Vault/AWS Secrets Manager to inject secrets (avoid .tfvars in Git).
- **Config Templating:**	Reuse base configurations across envs with overlay-specific variables (e.g., instance sizes).
- **Statefile Isolation:** Auto-configure separate remote state (S3/GCS paths) per environment.
- **Drift Detection:**	my-tf check-drift – Compare actual infra state against expected state per env. -->

### Estimated Impact
- 30% fewer environment-related outages
- 50% faster onboarding for junior engineers
- Eliminate “workspace dance” in Terraform workflows.

<!-- Installation instructions -->
### Installation

<!-- Directory structure explanation -->
### Directory Structure
The tool is provided as a single Python file (terranaut.py). 
Place it in your infrastructure repository root and follow the directory structure below.

.   
├── environments/           # Isolated environment configurations \
│   ├── dev/                # Development environment \
│   │   ├── aws/    
│   │   │   ├── main.tf        # Primary Infrastructure definition  
│   │   │   ├── variables.tf   # Environment-specific variables      
│   │   │   ├── outputs.tf     # Environment-specific outputs   
│   │   │   └── backend.tf     # State backend configuration (S3, GCS, etc.)    
│   │   └── azure/  
│   │       ├── main.tf     
│   │       ├── variables.tf     
│   │       ├── outputs.tf  
│   │       └── backend.tf  
│   │   
│   ├── staging/           # Staging environment    
│   └── prod/              # Production environment     
│   
├── shared_modules/        # Reusable infrastructure components     
│   ├── networking/        # Example: VPC module    
│   │   ├── main.tf     
│   │   ├── variables.tf    
│   │   └── outputs.tf      
│   │
│   ├── database/          # Example: RDS module    
│   └── ...                # Other reusable components      
│   
├── .tfenv                 # Active environment config (auto-generated)     
│   
└── terranaut.py               # The CLI tool (entry point)     

<!-- Detailed usage examples -->
### Usage Examples

<!-- Contribution guidelines -->
### Contribution

### Comparison with similar tools (Terragrunt, etc.)