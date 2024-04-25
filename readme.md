# Exploration Findings

## Are we allowed to use the latest community version at Zeiss

Legally we are not allowed to do so, the latest version requires for companies with a scale as large as ours to get the **Enterprise License**.

## What version are we allowed to use then

The package originally was under MIT Licence, but this changed starting `2023.x.x` version. Info from the author [here](https://github.com/QuestPDF/QuestPDF/issues/557#:~:text=This%20is%20correct.%20Only%20releases%202023.X.Y%20and%20beyond%20are%20under%20the%20new%20license.). Therefore the last version we are legally allowed to use is `22.12.x`. I have investigated the source code and it does have MIT license. It offered extended patches and support until **2024 Q1**.

## How does QuestPDF verify the licensing

Digging through the source code, I only found a `ValidateLicense()` function that only checks the identifier `QuestPDF.Settings.License` for validation, I could not find any networks flights for license verification. Verfied by sifting through all `http` urls in the source. Also [this](https://www.questpdf.com/license/configuration.html#code-change:~:text=The%20library%20does%20not%20require%20any%20license%20key.%20We%20trust%20our%20users%2C%20and%20therefore%20the%20process%20is%20simple.) from their official docs verify the findings.

I could analyze the network requests but I don't know if I am allowed to install wireshark on company laptops. 

## About the warnings

I did set up a sample project and migrated it to the latest stable version, tried all license types but still did not see any warning. Source code [here](https://github.com/sameert89/QuestPDFInvestigation.git).