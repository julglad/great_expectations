таблица ODS_PAYMENTS

user_id
batch.expect_column_values_to_not_be_null(column='user_id')  - поле user_id обязательно для заполнения
batch.expect_column_proportion_of_unique_values_to_be_between(column='user_id', max_value=0.1, min_value=0.01) - не должно быть слишком много повторяющихся значений, это может говорить об ошибке в данных 
batch.expect_column_values_to_be_in_type_list(column='user_id', type_list=['int8', 'BIGINT']) - поле user_id должно иметь тип BIGINT
pay_doc_type
batch.expect_column_values_to_be_in_set(column='pay_doc_type', value_set=['MASTER', 'MIR', 'VISA']) 
если тип платежного документа отличается от ['MASTER', 'MIR', 'VISA'], 
это может говорить об ошибке или о появлении нового типа платежного документа
batch.expect_column_values_to_not_be_null(column='pay_doc_type') - тип платежного документа обязателен для заполнения
pay_doc_num
batch.expect_column_values_to_not_be_null(column='pay_doc_num') - номер платежа обязателен для заполнения
batch.expect_column_values_to_be_in_type_list(column='pay_doc_num', type_list=['int8', 'BIGINT']) должно иметь тип BIGINT
account
batch.expect_column_values_to_not_be_null(column='account') обязателен для заполнения
batch.expect_column_values_to_match_regex(column='account', regex='FL-[0-9]{1,}') должен содержать 'FL-' и не менее одной цифры
phone
batch.expect_column_values_to_match_regex(column='phone', regex='\+79[0-9]{9}') должен содержать '+79' и 9 цифр
billing_period
batch.expect_column_values_to_be_between(column='billing_period', max_value='2021-12-31 00:00:00', min_value='2012-01-01 00:00:00') - так как таблица содержат данные за 2012-2021 года
batch.expect_column_values_to_not_be_null(column='billing_period')
pay_date
batch.expect_column_values_to_not_be_null(column='pay_date')
batch.expect_column_values_to_be_between(column='pay_date', max_value='2021-12-31 00:00:00', min_value='2012-01-01 00:00:00') - так как таблица содержат данные за 2012-2021 года
sum
batch.expect_column_values_to_be_between(column='sum', max_value=500000.0, min_value=0.01) - сумма  500000 слишком большая
batch.expect_column_values_to_not_be_null(column='sum')
batch.expect_column_values_to_be_in_type_list(column='sum', type_list=['NUMERIC', 'DECIMAL'])


таблица ODS_TRAFFIC

time_stamp
batch.expect_column_values_to_not_be_null(column='time_stamp')
batch.expect_column_values_to_be_in_type_list(column='time_stamp', type_list=['int8', 'BIGINT']) - время регистрации события в миллисекундах не может иметь тип отличный от BIGINT
user_id
batch.expect_column_values_to_not_be_null(column='user_id')
batch.expect_column_proportion_of_unique_values_to_be_between(column='user_id', max_value=0.1, min_value=0.01) - не должно быть слишком много повторяющихся значений, это может говорить об ошибке в данных 
batch.expect_column_values_to_be_in_type_list(column='user_id', type_list=['int8', 'BIGINT'])
device_serial
batch.expect_column_values_to_match_regex(column='device_serial', regex='d[0-9]{3}') - состоит из символа d и любых трех цифр
batch.expect_column_values_to_not_be_null(column='device_serial')
device_ip_addr
batch.expect_column_values_to_match_regex(column='device_ip_addr', regex='[0-9]{1,3}.[0-9]{1,3}.[0-9]{1,3}.[0-9]{1,3}') - ip-адрес должен состоять из 4-х групп от одного до трех символов, группы разделяются точкой 
batch.expect_column_values_to_not_be_null(column='device_ip_addr')
bytes_sent
batch.expect_column_values_to_not_be_null(column='bytes_sent')
batch.expect_column_values_to_be_in_type_list(column='bytes_sent', type_list=['int8', 'BIGINT']) - объем исходящего трафика должен иметь тип BIGINT
bytes_received
batch.expect_column_values_to_not_be_null(column='bytes_received')
batch.expect_column_values_to_be_in_type_list(column='bytes_received', type_list=['int8', 'BIGINT']) - объем входящего трафика должен иметь тип BIGINT

таблица ODS_BILLING
user_id
batch.expect_column_values_to_not_be_null(column='user_id')
batch.expect_column_proportion_of_unique_values_to_be_between(column='user_id', max_value=0.1, min_value=0.01) - не должно быть слишком много повторяющихся значений, это может говорить об ошибке в данных 
batch.expect_column_values_to_be_in_type_list(column='user_id', type_list=['int8', 'BIGINT'])
billing_period
batch.expect_column_values_to_be_between(column='billing_period', max_value='2021-12-31 00:00:00', min_value='2012-01-01 00:00:00') - так как таблица содержат данные за 2012-2021 года
batch.expect_column_values_to_not_be_null(column='billing_period')
sum
batch.expect_column_values_to_be_between(column='sum', max_value=500000.0, min_value=0.01) - сумма  500000 слишком большая
batch.expect_column_values_to_not_be_null(column='sum')
batch.expect_column_values_to_be_in_type_list(column='sum', type_list=['NUMERIC', 'DECIMAL'])

таблица ODS_ISSUE
user_id
batch.expect_column_values_to_not_be_null(column='user_id')
batch.expect_column_proportion_of_unique_values_to_be_between(column='user_id', max_value=0.1, min_value=0.01) - не должно быть слишком много повторяющихся значений, это может говорить об ошибке в данных 
batch.expect_column_values_to_be_in_type_list(column='user_id', type_list=['int8', 'BIGINT'])
