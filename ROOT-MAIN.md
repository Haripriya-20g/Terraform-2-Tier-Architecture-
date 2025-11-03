module "ec2" {
  source   = "./modules/ec2"
  key_name = "Feroz"  # Replace with your actual key name
}

module "rds" {
  source       = "./modules/rds"
  db_username  = "admin"
  db_password  = "feroz123"
}

output "ec2_public_ip" {
  value = module.ec2.public_ip
}

output "rds_endpoint" {
  value = module.rds.endpoint
