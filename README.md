# hugoEncrypt
Encrypt hugo pages, and decrypt them on the client
copy the encrypt.py file to the root of your hugo project

drop the decrypt.js file in the static/js folder of your hugo project
in your layout file, add the following line to the head section

```html
   {{ if .Params.hasEncryptedContent }} 
    <script src="/js/decrypt.js"></script>
    {{ end }}
```

in the front matter of the page you want to encrypt, add the following line

```yaml
hasEncryptedContent: true
```

in the `shortcodes` section of your blog. create a new file called `decrypt.html` and add the contents of decrypt.html 

## Usage

1. Encrypt the content of the markdown file using the script, like so

### Encrypt all pages in a directory

```bash
python3 -m hugoEncrypt.py <your_password> content/post/
```

and then you can run the hugo server to see the changes

```bash
hugo server
```

## TODO:

- [ ] reask for password if the password is incorrect