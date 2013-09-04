#PHP event2one API Client Library
----------------------------------
# Requirements: #
### API key ###

### User key ###


# Examples: #
### Load the API Client library ###

    require 'event2one.php';

### Initialize the client by setting your authentication tokens ###
Add your authentication tokens to make this example work:

    $e2o_client = new event2one( array('app_key'=>'YOUR_APP_KEY', 
                                       'user_key'=>'YOUR_USER_KEY'));
									   

									   
### getPartners example ###

try{
	$partners= $e2o->getPartners(array('id_event'=>'950'));
	
	if(is_array($partners)){

		echo '<table class="table">';
		foreach ($partners as $part){
			
			echo '<tr>
					<td>'.$part['id_contact']['id_contact'].'</td>
					<td>'.$part['prenom'].'</td>
					<td>'.$part['nom'].'</td>
					<td>'.$part['societe'].'</td>
					<td>'.$part['adresse'].'</td>
					<td>'.$part['cp'].'</td>
					<td>'.$part['tel'].'</td>
					<td>'.$part['mail'].'</td>
					<td>'.$part['port'].'</td>		
					<td>'.$part['statut'].'</td>
					<td>'.$part['fax'].'</td>
					<td>'.$part['web'].'</td>
					<td>'.$part['id_conf_event'].'</td>
				</tr>';
		}
		echo '</table>';
	}
}
catch (Exception $e){
	
	echo $e->getMessage();
}	
