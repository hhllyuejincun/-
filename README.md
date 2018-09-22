<?php

/**
 * email smtp （support php7）
 *
 * Modified by: Reson 2017/06
 * UPDATE:
 * 1、change ereg to preg_match；change ereg_replace to preg_replace.
 * 2、change var to public/private.
 *
 * More: http://www.daixiaorui.com
 *
 */


class Smtp
{
    /* Public Variables */
    public $smtp_port;

    public $time_out;

    public $host_name;

    public $log_file;

    public $relay_host;

    public $debug;

    public $auth;

    public $user;

    public $pass;

    /* Private Variables */
    private $sock;

    /* Constractor */
    function __construct($relay_host = "", $smtp_port = 25,$auth = false,$user,$pass)
    {
        $this->debug = FALSE;

        $this->smtp_port = $smtp_port;

        $this->relay_host = $relay_host;

        $this->time_out = 30; //is used in fsockopen()


        $this->auth = $auth;//auth

        $this->user = $user;

        $this->pass = $pass;
