magento
=======

Billmate payment plugin for magento firecheckout


=====	for firecheckout only ======


insert following code in billing.phtml and this file can found under
app\design\frontend\default\hultens\template\firecheckout\checkout or app\design\frontend\default\default\template\firecheckout\checkout )


$fields['person_number'] = array(
           'class'  => 'input-text',
           'label'  => 'Person Number',
           'status' => 'required'
       );

after 

   $fields = array(
       'name'  => array(),
       'email' => array(
           'class'  => 'input-text validate-email',
           'label'  => 'Email Address',
           'status' => $_isCustomerLoggedIn ? 'hidden' : 'required'
       ),
       'person_number' => array(
           'class'  => 'input-text',
           'label'  => 'Person Number',
           'status' => 'required'
       ),
       'company' => array(
           'class' => 'input-text',
           'label' => 'Company'
       ),
       'fax' => array(
           'class' => 'input-text',
           'label' => 'Fax'
       ),
       'telephone' => array(
           'class' => 'input-text',
           'label' => 'Telephone'
       ),
       'city' => array(
           'class' => 'input-text',
           'label' => 'City'
       ),
       'postcode' => array(
           'class' => 'input-text validate-zip-international',
           'label' => 'Zip/Postal Code'
       ),
       'street1' => array(
           'class' => 'input-text',
           'label' => 'Address',
           'title' => 'Street Address',
           'name'  => $_prefix . '[street][]',
           'value' => $_address->getStreet(1)
       ),
       'country_id' => array(
           'label' => 'Country',
           'required_to_render' => 1
       ),
       'region' => array(
           'label' => 'State/Province',
           'required_to_render' => 1
       ),
       'dob' => array(
           'status' => (!$_isCustomerLoggedIn && $_dob->isEnabled()) ? 'optional' : 'hidden'
       ),
       'gender' => array(
           'status' => (!$_isCustomerLoggedIn && $_gender->isEnabled()) ? 'optional' : 'hidden'
       ),
       'taxvat' => array(
           'status' => (!$_isCustomerLoggedIn && $_taxvat->isEnabled()) ? 'optional' : 'hidden'
       )
   );

edit file \app\code\local\TM\FireCheckout\etc\system.xml
