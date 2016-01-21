<?php
/**
 * The edit form class for this question type. Each time a question is created moodle uses the
 * edit form to collect data from the teacher. With this form the following attributes of a question 
 * need to be defined: name, question text, geven code and the JUnit test class. Affter editing this 
 * form a question is created in the database with the form's attributes.
 *
 * @package    qtype
 * @subpackage javaunittest
 * @author     Gergely Bertalan, bertalangeri@freemail.hu
 * @reference  sojunit 2008, Süreç Özcan, suerec@darkjade.net
 * @license    http://www.gnu.org/copyleft/gpl.html GNU GPL v3 or later
 */
defined ( 'MOODLE_INTERNAL' ) || die ();

/**
 * javaunittest question type editing form
 */
class qtype_javaunittest_edit_form extends question_edit_form {
    protected function definition_inner ( $mform ) {
        global $DB, $question, $PAGE;
        
        $loaded_initialy = optional_param ( 'reloaded_initialy', 1, PARAM_INT );
        
        $qtype = question_bank::get_qtype ( 'javaunittest' );
        
        $definitionoptions = $this->_customdata['definitionoptions'];
        $attachmentoptions = $this->_customdata['attachmentoptions'];
        
		
        
        // -------------------------- feedback options
        $mform->addElement ( 'select', 'feedbacklevel', get_string ( 'feedbacklevel', 'qtype_javaunittest' ), 
                $qtype->feedback_levels () );
        $mform->setDefault ( 'feedbacklevel', FEEDBACK_ONLY_TIMES );
        
	// -------------------------- auditlevel options
        $mform->addElement ( 'select', 'auditlevel', get_string ( 'auditlevel', 'qtype_javaunittest' ), 
                $qtype->audit_values () );
        $mform->setDefault ( 'auditlevel', AUDIT_VALUE_30 );
        
        // -------------------------- size of the response field
        $mform->addElement ( 'select', 'responsefieldlines', get_string ( 'responsefieldlines', 'qtype_javaunittest' ), 
                $qtype->response_sizes () );
        $mform->setDefault ( 'responsefieldlines', 15 );
        
        // -------------------------- "Given Code" Text-Area Modded
		/*$attributes['rows'] = 20;
        	$attributes['cols'] = 80;		

		$init_page  = '<script language="javascript" type="text/javascript" ';
		$init_page .= 'src="/mod/editarea_0_8_2/edit_area/edit_area_full.js"></script> ';
		#$init_page .= 'src="http://www.cdolivet.com/editarea/editarea/edit_area/edit_area_full.js"></script> ';
		#$init_page .= 'src=" http://lms-test2.eigsi.fr/inc/edit_area/edit_area_full.js"></script> ';
		$init_page .= '<script language="javascript" type="text/javascript"> ';
		$init_page .= 'editAreaLoader.init({id : "' . $attributes['id'] . '",syntax: "java",start_highlight: true,is_editable: ' . 'true' .' }); ';
		$init_page .= ' </script> ';			
		 
		$mform->addElement ( 'textarea', 'givencode', get_string ( 'givencode', 'qtype_javaunittest' ), 
                array (
                        'cols' => 80,
                        'rows' => 20,
                ) );
				
				
		
        $mform->setType ( 'givencode', PARAM_RAW );
        $mform->addHelpButton ( 'givencode', 'givencode', 'qtype_javaunittest' );
        */

	 // -------------------------- "Given Code" Text-Area
        $mform->addElement ( 'textarea', 'givencode', get_string ( 'givencode', 'qtype_javaunittest' ), 
                array (
                        'cols' => 80,
                        'rows' => 20 
                ) );
        $mform->setType ( 'givencode', PARAM_RAW );
        $mform->addHelpButton ( 'givencode', 'givencode', 'qtype_javaunittest' );
        // -------------------------- "Test class" Text-Area
        $mform->addElement ( 'textarea', 'testclassname', get_string ( 'testclassname', 'qtype_javaunittest' ), 
                array (
                        'cols' => 80,
                        'rows' => 1 
                ) );
        $mform->setType ( 'testclassname', PARAM_ALPHANUMEXT );
        $mform->addRule ( 'testclassname', null, 'required' );
        $mform->addHelpButton ( 'testclassname', 'testclassname', 'qtype_javaunittest' );
        $mform->addElement ( 'textarea', 'junitcode', get_string ( 'uploadtestclass', 'qtype_javaunittest' ), 
                array (
                        'cols' => 80,
                        'rows' => 20 
                ) );
        $mform->setType ( 'junitcode', PARAM_RAW );
        $mform->addRule ( 'junitcode', null, 'required' );
        $mform->addHelpButton ( 'junitcode', 'uploadtestclass', 'qtype_javaunittest' );
    }
    public function qtype () {
        return 'javaunittest';
    }
}
