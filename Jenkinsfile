node {
  stage('checkout') {
        checkout scm
  }

  /* If updated_image is true , then it will create a new TD and New service, else it will create a new TD Revision and update the
  existing Service */
  stage('Automating') {
       def instances=params.No_of_Instances_required
       def image=params.EC2_Image_ID
       if (params.Automation_Type == 'Full_Automation')
       {
         sh ("cd /opt/terransijenk/terraform/dev && terraform plan -out=tfplan -input=false -var='insta_count='${instances}'' -var='ami_type='${image}'' -auto-approve -lock=false") 
      /*   sh ("cd /opt/terransijenk/terraform/dev && terraform apply -var='insta_count='${instances}'' -var='ami_type='${image}'' -auto-approve -lock=false -no-color -out=create.tfplan") 
         
         sh "cd /opt/terransijenk/ansible && sleep 30; ANSIBLE_HOST_KEY_CHECKING=False ansible-playbook -u ubuntu -e '(image_id='${image}'' --private-key Jenkins.pem -i invent.txt, installdocker.yml"      
       */
       }      
       
      
   }
}


