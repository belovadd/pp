erDiagram
    users ||--o{ books : "создает (user_id)"
    users ||--o{ book_rates : "оценивает (user_id)"
    books ||--o{ book_rates : "получает оценку (book_id)"
    users ||--o{ libraries : "владеет (user_id)"
    libraries ||--o{ library_books : "содержит (library_id)"
    books ||--o{ library_books : "находится в (book_id)"
    users ||--o{ library_books : "добавляет (user_id)"
    
    users ||--o{ reading_sessions : "проводит (user_id)"
    books |o--o{ reading_sessions : "читается в (book_id)"
    users ||--|| timer_settings : "настраивает (user_id)"
    users ||--|| plant_states : "выращивает (user_id)"
    users ||--o{ plant_stage_history : "сохраняет историю (user_id)"
    users ||--o{ reading_goals : "устанавливает (user_id)"
    
    users ||--o{ friend_requests : "отправляет/получает (user_id)"
    users ||--o{ friendships : "состоит в (user_id)"
    
    users ||--o{ book_clubs : "создает (user_id_creator)"
    book_clubs ||--o{ book_club_members : "включает (club_id)"
    users ||--o{ book_club_members : "участвует (user_id)"
    book_clubs ||--o{ book_club_messages : "содержит (club_id)"
    users ||--o{ book_club_messages : "пишет (user_id)"
    
    book_clubs ||--o{ book_club_publications : "публикует (club_id)"
    users ||--o{ book_club_publications : "автор (user_id)"
    books |o--o{ book_club_publications : "упоминается (book_id)"
    book_club_publications ||--o{ book_club_publication_comments : "комментируется (publication_id)"
    users ||--o{ book_club_publication_comments : "комментирует (user_id)"
    
    users ||--o{ user_publications : "создает пост (user_id)"
    books |o--o{ user_publications : "упоминается (book_id)"
    user_publications ||--o{ user_publication_comments : "комментируется (publication_id)"
    users ||--o{ user_publication_comments : "комментирует (user_id)"
    
    users ||--o{ user_messages : "отправляет/получает (user_id)"