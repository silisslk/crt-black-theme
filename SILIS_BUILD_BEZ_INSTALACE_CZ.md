# SILIS Black: sestavení bez instalace programů na vlastní PC

Obsahuje workflow `.github/workflows/silis-miyoo-arm.yml`.

## Co workflow dělá

1. Na GitHub Actions serveru stáhne OnionUI/Onion.
2. Spustí ARM toolchain v Dockeru pouze na serveru GitHubu.
3. Zkontroluje `libsqlite3.so`, `libshmvar.so` a SQLite hlavičky.
4. Pokusí se spustit `make device` a ověřit ELF pro Miyoo Mini Plus.
5. **Jen při úspěchu** vystaví ke stažení ARM soubor `MainUI-354-SILIS-TEST` v sekci Artifacts.

## Co musíš udělat v prohlížeči

- Přihlásit se ke GitHubu a založit nový (ideálně soukromý) repozitář.
- Nahrát do něj **obsah** tohoto rozbaleného ZIPu, včetně skryté složky `.github`.
- V repozitáři otevřít Actions -> SILIS Black - Miyoo Mini Plus ARM build -> Run workflow.
- Po dokončení zkontrolovat zelený/červený výsledek a případné chybové hlášení.
- Pokud proběhne zeleně, stáhnout soubor v Artifacts.

## Omezení

Tento postup nelze zkontrolovat vykonáním GitHub Actions z tohoto prostředí. Úspěch je podmíněn dostupností Docker image a knihoven ve staženém Onion checkoutu. Pokud chybí, workflow skončí červeně a nevyrobí nebezpečný/neudělaný ARM balíček. Je to **automatizovaný pokus o sestavení**, nikoli potvrzený build.

**Neinstaluj testovací binárku na hlavní SD kartu.** Nejdříve zálohuj a použij kopii karty. Nic z workflow nemění napájení OnionOS. Váš dosavadní SROL Studio zůstává nedotčené.
