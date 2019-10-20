node {
  stage('checkout') {
        checkout scm
  }

  /* If updated_image is true , then it will create a new TD and New service, else it will create a new TD Revision and update the
  existing Service */
  stage('Stage:TD & Service') {
       def instances=params.No_of_Instances_required
       def image=params.EC2_Image_ID
       if (params.Automation_Type == 'Full_Automation')
  
       {
       sh 'cd /opt/terransijenk/terraform/dev'
         sh 'terraform apply -var=insta_count=[${instances}] -var=ami_type=[${image}] -auto-approve' 
       }      
       
      
   }
}


