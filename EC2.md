resource "aws_instance" "app_server" {
  ami           = "ami-02d26659fd82cf299"  # Amazon Linux 2 AMI (update for your region)
  instance_type = "t2.micro"
  key_name      = var.key_name

  associate_public_ip_address = true
}

variable "key_name" {
  description = "SSH key pair name"
  type        = string
}

output "public_ip" {
  value = aws_instance.app_server.public_ip
}