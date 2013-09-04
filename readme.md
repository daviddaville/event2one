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
		$partners= $e2o->getPartners(array('id_event'=>ID_EVENT));
	
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


### contact_get example ###
 
		 try{
		 	$contact= $e2o->contact_get(array(	'id_event'=>'ID_EVENT', 
		 						'id_contact'=>ID_CONTACT)
		 								);
		  	echo '<table class="table">
		 		<tr>
		 			<td>'.utf8_decode($contact['prenom']).'</td>
		 			<td>'.utf8_decode($contact['nom']).'</td>
					<td>'.utf8_decode($contact['fonction']).'</td>
		 			<td>'.utf8_decode($contact['societe']).'</td>
		 			<td>'.utf8_decode($contact['edito_long']).'</td>
		 			<td>'.utf8_decode($contact['edito_court']).'</td>
				</tr>
			</table>';
		 }
		 catch (Exception $e){
		 
		 	echo $e->getMessage();
		 }
