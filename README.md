# ansible
learning of ansible


        --------------
        [ Control Box]        # Ansible
        ---------------
              |
              |
              |
      ------------------
        [loadbalancer]        #Nginx
      -------------------
        |              |
        |              |
      ------       ---------
      [app01]       [app02]        #Apache
      -------       ---------
         |              |
         |              |
         ----------------
         [DataBase db01]        #mariadb
         ----------------
