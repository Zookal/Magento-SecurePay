Magento-SecurePay
=================

Unofficial repository for the Magento SecurePay SecureXML module with patches.

Code pool has been moved to `community`. The aligent version has code pool `local` which is in some constellations not useful.

### Patches

```
+    protected $_canRefundInvoicePartial = true;
```

```
-    protected $_formBlockType = 'SecurePay_Sxml_block_form_cc';
+    protected $_formBlockType = 'Sxml/form_cc';
```

```
+            $payment->setCcTransId(''.$transaction_id);
+            $payment->setTransactionId(''.$transaction_id);
```

In authorize() and capture():

```
-            Mage::throwException("" . $error);
+            throw new Mage_Payment_Model_Info_Exception((string)$error);
```

useful in OnePageController::saveOrderAction()

Offical extension in the [Magento Store](http://www.magentocommerce.com/magento-connect/official-securepay-xml-api-au.html).


