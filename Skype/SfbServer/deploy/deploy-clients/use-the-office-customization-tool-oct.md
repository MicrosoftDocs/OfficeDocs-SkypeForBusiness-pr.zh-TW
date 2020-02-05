---
title: 在商務用 Skype Server 中使用 Office 自訂工具（OCT）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
description: 摘要：如何在商務用 Skype 用戶端使用 Office 自訂工具。
ms.openlocfilehash: d5b9e5363f56842675831c4b3c0fe3582fb6d02a
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768446"
---
# <a name="use-the-office-customization-tool-oct-in-skype-for-business-server"></a>在商務用 Skype Server 中使用 Office 自訂工具（OCT）
 
**摘要：** 如何在商務用 Skype 用戶端使用 Office 自訂工具。
  
Office 自訂工具（OCT）是安裝程式的一部分，且是許多自訂的建議工具。 使用 OCT，您可以自訂 Office，並在安裝程式自訂 .msp 檔案中儲存您的自訂專案。 您將檔案放在網路安裝點的 [更新] 資料夾中。 當您安裝 Office 時，安裝程式會在 [更新] 資料夾中尋找安裝程式自訂檔案，並套用自訂專案。 [更新] 資料夾只能用來在初次安裝 Office 時部署軟體更新。
  
OCT 是設定的一部分，且僅適用于大量授權版本的產品。 您可以從包含 Office 來源`setup.exe /admin`檔案之網路安裝點的根目錄，在命令列上輸入，以執行 OCT。 例如，請使用下列程式：
  
 ```console
\\server\share\Office15\setup.exe /admin
```
  
系統管理員使用 OCT 建立安裝程式自訂 .msp 檔案，並可自訂下欄區域：
  
- **設定**用來指定用戶端和預設組織名稱、其他網路安裝來源、產品金鑰、使用者授權合約、顯示階層、舊版 Office 的預設安裝位置、要在安裝期間執行的自訂程式、安全性設定和安裝屬性。
    
- **功能**用來設定使用者設定，並自訂 Office 功能的安裝方式。 系統管理員可以使用 OCT 為使用者指定 Office 應用程式設定的初始預設值。 使用者可以在安裝之後修改大部分的設定。
    
- **其他內容**用來新增或移除檔案、新增或移除登錄機碼目，以及設定快速鍵。
    
- **Outlook**用來自訂使用者的預設 Outlook 設定檔、指定 Exchange 設定、新增帳戶、移除帳戶和匯出設定，以及指定 Send\Receive 群組。
    
如需 OCT 的相關資訊，請參閱[使用 OCT 自訂 Office 2013](https://docs.microsoft.com/previous-versions/office/office-2013-resource-kit/cc179132(v=office.15))。 請注意，這項資訊也適用于更新版本的 Office。
  

