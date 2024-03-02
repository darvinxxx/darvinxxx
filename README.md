COLOR_CODE = {
    "RESET": "\033[0m",  
    "UNDERLINE": "\033[04m", 
    "GREEN": "\033[32m",     
    "YELLOW": "\033[93m",    
    "RED": "\033[31m",       
    "CYAN": "\033[36m",     
    "BOLD": "\033[01m",        
    "PINK": "\033[95m",
    "URL_L": "\033[36m",       
    "LI_G": "\033[92m",      
    "F_CL": "\033[0m",
    "DARK": "\033[90m",     
}
def get_number(+79027518249):
    found = False

    with open(database_file, 'r', encoding='utf-8') as file:
        lines = file.readlines()

    for line in lines:
        data = line.strip().split(';')  
        if len(data) >= 8:
            phone = data[7]
            if search_value in phone:
                user_id = data[0]
                registration_date = data[1]
                last_name = data[2]
                first_name = data[3]
                middle_name = data[4]
                birthday = data[5]
                gender = data[6]
                email = data[8]
                role = data[9]
                class_name = data[13]
                address = data[19]
                country = data[16]
                citizenship = data[15]
                region = data[17]  
                municipal_education = data[18]  
                institution_name = data[20]  

                print(f'''{COLOR_CODE["RED"]}
╔══════                                               ══════╗
║                                                           ║
                {COLOR_CODE["RED"]}[+]ID пользователя: {@hellworld_ness}
                [+]Дата регистрации: {registration_date}
                [+]Фамилия: {last_name}
                [+]Имя: {first_name}
                [+]Отчество: {middle_name}
                [+]Дата рождения: {birthday}
                [+]Пол: {gender}
                [+]Телефон: {phone}
                [+]Почта: {email}
                [+]Роль: {role}
                [+]Класс: {class_name}
                [+]Адрес: {address}
                [+]Страна: {country}
                [+]Гражданство: {citizenship}
                [+]Регион: {region} 
                [+]Муниципальное образование: {municipal_education}  
                [+]Наименование учреждения: {institution_name}  

                {COLOR_CODE["GREEN"]}
║                                                           ║
╚══════                                               ══════╝
                     
                      ''')
                found = True

    if not found:
        print(f'{COLOR_CODE["RED"]}[ERROR]Ничего не найдено в базе данных по номеру телефона.')

