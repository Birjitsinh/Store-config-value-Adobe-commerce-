# Store-config-value-Adobe-commerce-

how to retrive updated value in rabbit mq consumer.
in adobe commerce getting old store configuration data. use Belellow method to get updated data in consumer file.
,,,
 use Magento\Framework\App\Config\ReinitableConfigInterface as ConfigInterface;
 
 /**
   * Client constructor
   *
   * @param ConfigInterface $config
   */
 public function __construct(
     private ConfigInterface $config
 ) {
 }
 //Call this in method your 
  $this->config->reinit();    

,,,
