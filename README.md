SimpleSpec  
=================================
PHP SimpleTest extension for Behavior driven development(BDD), An extension class for SimpleTest


why not PHPSpec? well its a good project but SimpleTest i want something simpler

Features
------------------
  - Reuse SimpleTest framework
  - simplly one include from away
  - Underscore for readibility - all examples uses underscore to seperate descriptions.
  - Natural language grammer
  - before_all, after_all is not supported, i don't want to modify SimpleTest
  - conventional before/after named prepare/cleanup respectively

Requirement
-------------------
 - PHP 5.1 +
 - SimpleTest installed

Example
------------------

    <?php
    require 'spec_helper.php';
    
    class Describe_his_mum extends SimpleSpec {
        function prepare() {
            $this->mum = new Mum(array('mood'=>'angry')); 
        }

        function should_be_very_angry_when_i_break_my_lunch_box() {
            expects($this->mum->mood)->should_be('angry');
        }

       function should_be_very_happy_when_i_punch_her_in_the_face() {
            punch($this->mum);
            expects($this->mum->mood)->should_be('happy');
        }

        function cleanup() {
            unset($this->mum); // kill da mum
        }
    }
    
    ?>
 
 
Author 
----------------
 Taylor Luk aka 'speedmax'
 
 
license Free for all  
---------------------
