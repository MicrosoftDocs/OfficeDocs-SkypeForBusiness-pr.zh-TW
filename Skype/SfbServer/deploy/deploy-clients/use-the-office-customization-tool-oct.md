---
title: '在商務用 Skype Server 中使用 Office 自訂工具 (OCT) '
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 摘要：如何搭配商務用 Skype 用戶端使用 Office 自訂工具。
---

# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>在商務用 Skype Server 中使用 Office 自訂工具 (OCT) 
 
**總結：** 如何搭配商務用 Skype 用戶端使用 Office 自訂工具。
  
Office 自訂工具 (OCT) 屬於安裝程式的一部分，也是許多自訂的建議使用工具。 您可以使用 OCT 自訂 Office，並將自訂儲存在安裝程式自訂 .msp 檔案中。 您將此檔案放在網路安裝點上的 Updates 資料夾中。 當您安裝 Office 時，安裝程式會在 Updates 資料夾中尋找安裝程式自訂檔案，並套用自訂。 「更新」資料夾只可用於在 Office 初始安裝期間部署軟體更新。
  
OCT 是安裝程式的一部分，只用于大量授權版本的產品。 您可以從包含 Office 來源檔案之網路安裝點的根目錄輸入 `setup.exe /admin` 命令列，以執行 OCT。 例如，使用下列程式：
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
管理員使用 OCT 建立安裝程式自訂 .msp 檔案，並可自訂下欄區域：
  
- **設置** 用於指定用戶端的預設安裝位置和預設組織名稱、其他網路安裝來源、產品金鑰、使用者授權合約、顯示層級、要移除的舊版 Office、安裝期間要執行的自訂程式、安全性設定，以及安裝程式屬性。
    
- **特徵** 用於設定使用者設定，以及自訂安裝 Office 功能的方式。 系統管理員可以使用 OCT 來指定使用者 Office 應用程式設定的初始預設值。 使用者可以在安裝之後修改大部分的設定。
    
- **其他內容** 用於新增或移除檔案、新增或移除登錄專案，以及設定快捷方式。
    
- **Outlook** 用於自訂使用者的預設 Outlook 設定檔、指定 Exchange 設定、新增帳戶、移除帳戶和匯出設定，以及指定傳送/接收群組。
    
如需 OCT 的詳細資訊，請參閱[使用 oct 自訂 Office 2013](/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))。 請注意，此資訊也適用于更新版本的 Office。
