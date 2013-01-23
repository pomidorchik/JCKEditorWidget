# JCKEditorWidget

Yii виджет для подключения CKEditor. Работает как с третьей так и с четвертой версией редактора.

## Использование

*   Скопируйте файл `JCKEditorWidget.php` в директорию `protected` вашего приложения, например `protected/extensions/JCKEditor/JCKEditorWidget.php`

*   Подключите расширение [SmartClientScript](https://github.com/pomidorchik/SmartClientScript).   

*   Воспользуйтесь виджетом в файле представления.
        
        <div class="row">
    		<?php echo $form->labelEx($model,'text'); ?>
			<?php echo $form->textArea($model,'text',array('rows'=>6, 'cols'=>50, 'id'=>'Champion_text_CK')); ?>
			<?php echo $form->error($model,'text'); ?>
		</div>

		<?php $this->widget('ext.JCKEditor.JCKEditorWidget', array(
			'id' => 'Champion_text_CK',        
			'height' => '200px',
			'width' => '400px',
			'toolbar' => 'myToolbar',
			'path' => Yii::app()->getBaseUrl(true).'/ckeditor4/',
			'config'=>array(
				'language'=> 'ru',
			)
		)); ?>
        
## Настройки

*   <code>id</code> - <code>id</code> поля к которому подключается редактор
*   <code>height</code> - высота редактора.
*   <code>width</code> - ширина редактора.
*   <code>toolbar</code> - панель инстументов. Она должна быть определена в файле настроек config.js редактора.
*   <code>path</code> - абсолютный путь к каталогу с CKEditor (со слешем на конце).
*   <code>config</code> - дополнительные настройки. Это массив типа ключ-значение, в котором можно использовать любые настройки из документации к CKEditor.