**GENEROWANIE I ZAPIS KLUCZA**
1. sh-keygen -t ed25519 -C "mojemail@gmail.com" --- **generuje nowy klucz ssh**
2. pbcopy < ~/.ssh/id_ed25519.pub --- **kopiuje klucz, aby następnie wprowadzić go w githubie**
3. ls -la --- **wyswietla listę, wśród której szukam folderu .ssh**
4. eval $(ssh-agent) --- **dodanie klucza**
5. ssh-add ~/.ssh/id_rsa --- **dodanie klucza**

**TWORZENIE OBRAZU**
1.  DOCKER_BUILDKIT=1 docker build -f Desktop/folder/dockerfile3 Desktop/folder --ssh default --- **tworzy obraz**
2.  docker images --- **wyświetla listę obrazów**
3.  docker run -p 8080:8080 <IMAGE_ID> --- **uruchamia obraz z przekierowaniem portow**

**PRZESŁANIE DO DOCKERHUB**
1. docker login --- **logowanie do dockerhub**
2. docker images --- **wyświetla listę obrazów**
3. docker tag <IMAGE_ID> <NAZWA_DLA_DOCKERHUB> --- **ustalenie tagu**
4. docker push <NAZWA_DLA_DOCKERHUB>:<TAG>
