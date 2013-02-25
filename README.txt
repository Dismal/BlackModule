BlackModule
@author Dmitry Kuznetsov (https://github.com/Dismal/BlackModule)
@version 1.0

This module protects your website content from being copied.
The following arrangements will not guarantee the safety of the content, and are not recommended for old popular
sites, but for new sites it can be useful:
- Disabling shortcut keys Ctrl+C, Ctrl+X, Ctrl+A, Ctrl+U
- Disabling the context menu on the site
- Disabling .oncopy and .ondragstart js events
- When the visitor try to copy a large amount of text (more then 200 characters)
or try to view the source code current ip is added to the list of banned and cookies is installed in the browser.
- If visitors User-Agent found in the list of known spam bots and parsers, the current ip is added to the list of
banned.

Installation:

1. Add the table 'banned' in your database (import the file sql/banned.sql), do not forget to add a table prefix,
if you use it in your application.
2. Extract the files into your modules folder (for example, /protected/modules/).
3. Edit your configuration file to register the module:
	'modules'=>array(
	    ...
		'black'
	),
	
4. Add widget to your pages:
<? Yii::app()->getModule('black'); $this->widget('NoCopyWidget'); ?>

 ****************************************
 
BlackModule

������ ������ �������� ������� ����� �� �����������.
��������� ���� �� ����������� ����������� ���������� �����, � �� ������������� ��� ������ � ���������� ������,
�� ��� ������� ������ ����� ��������� ���������:
- ���������� ��������� ������ Ctrl+C, Ctrl+X, Ctrl+A, Ctrl+U
- ���������� ������������ ���� �� ��������� �����
- ������ ����������� (.oncopy) � �������������� (.ondragstart) �� ��������� �����
- ��� ������� ����������� ������� ����� ������ (����� 200 ��������) ��� ��� ��������� ��������� ���� ����� ip
���������� ������������ � ������ ����������, ����� � ������� ��������������� cookies.
��� ������� cookies � ������ � ������� ip, �� ����� ����������� � ���;
��� ������ � ����������� ip � ������� ��������, ����� ��������������� cookies.
- ��� ���������� User-Agent ���������� �� ������� ��������� ����-����� � �������� ip ����������� � ������ ����������.

���������:

1. �������� ������� banned � ���� ���� ������, �������� ������ ����� sql/banned.sql,
�� �������� �������� ������� ������, ���� �� ����������� ��� � ����� ����������.
2. ���������� ����� � ���� ����� ������� (��������, /protected/modules/)
3. �������� ������ � ������ �����:
	'modules'=>array(
		...
		'black'
	),
	
4. �������� ������ �� �������� �����:
<? Yii::app()->getModule('black'); $this->widget('NoCopyWidget'); ?>
