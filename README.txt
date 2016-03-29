// cara instal
- Copy config/gcm.php ke folder config
- Copy libraries/gcm.php ke folder libraries


// contoh penggunaan
public function gcm()
{
	// load library
	$this->load->library('gcm');
	
	// seting message
	$this->gcm->setMessage('Test message from CI');
	
	// add receiver
	$this->gcm->addRecepient('DEVICE_ID_RECEPIENT');
	//$this->gcm->addRecepient('New reg id');
	
	// then send
	if ($this->gcm->send())
		echo 'Success for all messages';
	else
		echo 'Some messages have errors';

	// and see responses for more info
	print_r($this->gcm->status);
	print_r($this->gcm->messagesStatuses);
}
