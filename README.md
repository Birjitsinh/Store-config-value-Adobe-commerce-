# Store-config-value-Adobe-commerce-

Retrieve Updated Value in RabbitMQ Consumer for Adobe Commerce

When working with RabbitMQ in Adobe Commerce, you might encounter a scenario where the consumer retrieves outdated store configuration data instead of the updated values. This can be resolved by using the correct method to fetch the updated store configuration in the consumer file.

Problem

By default, store configuration values might be cached, leading to the consumer processing old data. This can cause inconsistencies, especially when the configuration has recently changed.

Solution

To retrieve the updated store configuration data in your RabbitMQ consumer, use the following approach:

```php
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

public function proceed(string $msg)
{
 //Call this in method your 
  $this->config->reinit();
}


```
