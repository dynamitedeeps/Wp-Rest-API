# Wp-Rest-API
<?php 
/* SSo Check API*/

/**
 * 
 */
class Ssocheck extends WP_REST_CONTROLLER
{

	var $my_namespace = 'my_rest_server/v1';
	
	function __construct()
	{
		// register_routes();
		add_action('rest_api_init',array( $this, 'register_routes'));
	}

	public function register_routes(){

		register_rest_route('v1', '/allusers/', array(
        	'methods' => 'GET',
        	'callback' => array($this, 'get_users_data'),
    	));

	}

	public function get_users_data(){

		return get_users();

	}
}

$check = new Ssocheck(); 
