---
title: 商務用 Skype Online 委派的設定和疑難排解
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: e676b911-5f82-41d8-b4ce-3d0d45c3cd04
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 本文將說明如何設定和疑難排解線上委派商務用 Skype疑難排解。 本文提供設定建議、最佳做法和疑難排解步驟的指引。
ms.openlocfilehash: c672006e8b78e5b3fb881da97e2ab3bbe65e465aa5981cc95fb2caf9bed39e4f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54310172"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>商務用 Skype Online 委派的設定和疑難排解

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

本文將說明如何設定和疑難排解線上委派商務用 Skype疑難排解。 本文提供設定建議、最佳做法和疑難排解步驟的指引。
  
## <a name="guidelines-and-requirements"></a>指導方針和需求

### <a name="guidelines-for-delegation"></a>委派指導方針

設定及讓委派正確工作取決於您遵循下列指導方針：
  
- 您必須在 2015 完整商務用 Skype用戶端使用最新更新，或使用 2016 商務用 Skype完整用戶端。
    
- 您必須使用具有最新Outlook的 2013 用戶端，或 Outlook 2016用戶端。
    
- 請確定委派器和代理人電腦有一Outlook為主要或預設設定檔的郵件設定檔。 該郵件設定檔應只包含一個帳戶。
    
- 商務用 Skype代理人和代理人的代理人應為線上使用者。 此外，Exchange Server帳戶的信箱必須同時為 Online 或兩者都是內部部署。
    
- 委派者與代理人應該使用相同的主要版本Outlook。
    
- **在用戶端策略中，EnableExchangeDelegateSync** 屬性值應該設為 true。 您可以在線上 PowerShell 模組中商務用 Skype **Get-CSClientPolicy** Cmdlet 來驗證此設定。
    
- 委派者與代理人必須同時在不同工作站上商務用 Skype Outlook和代理人。
    
- 線上委派不支援共用商務用 Skype信箱。 這是因為共用信箱沒有傳送代理存取控制清單 (ACL ) 。
    
### <a name="skype-for-business-client-version-support"></a>商務用 Skype用戶端版本支援

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/商務用 Skype基本用戶端**| 不支援 |不支援
|**商務用 Skype 2015**|支援| 支援|
|**商務用 Skype 2016**|支援| 支援|

   
### <a name="licensing-requirements"></a>授權需求

**EnterpriseE3 授權案例**

|**許可證**|**用戶端**|**注釋**|
|:-----|:-----|:-----|
|EnterpriseE3  <br/> |Lync 2013 (商務用 Skype 2015) 2013 Outlook 2013 或 Outlook 2016  <br/> 商務用 Skype 2016 與 2013 Outlook 2016 一Outlook 2016  <br/> |商務用 Skype基本用戶端不支援委派。  <br/> 對於 Mac 用戶端，您可以委派通話，但無法委派會議。  <br/> |
|EnterpriseE3 Office 365 電話系統 + Office 365 xCalling 方案  <br/> |Lync 2013 (商務用 Skype 2015) 2013 Outlook 2013 或 Outlook 2016  <br/> 商務用 Skype 2016 與 2013 Outlook 2016 一Outlook 2016  <br/> Lync for Mac 2011  <br/> |商務用 Skype基本用戶端不支援委派。  <br/> 對於 Mac 用戶端，您可以委派通話，但無法委派會議。  <br/> |
   
**EnterpriseE5 授權案例**

|**許可證**|**用戶端**|**注釋**|
|:-----|:-----|:-----|
|EnterpriseE5  <br/> |Lync 2013 (商務用 Skype 2015) 2013 Outlook 2013 或 Outlook 2016。  <br/> 商務用 Skype 2016 與 2013 Outlook 2016 一Outlook 2016  <br/> |商務用 Skype基本用戶端不支援委派。  <br/> 對於 Mac 用戶端，您可以委派通話，但無法委派會議。  <br/> |
|EnterpriseE5 加 Office 365通話方案  <br/> |Mac 版商務用 Skype 2016  <br/> Lync 2013 (商務用 Skype 2015) 2013 Outlook 2013 或 Outlook 2016  <br/> 商務用 Skype 2016 與 2013 Outlook 2016 一Outlook 2016  <br/> Lync for Mac 2011  <br/> |商務用 Skype基本用戶端不支援委派。  <br/> 對於 Mac 用戶端，您可以委派通話，但無法委派會議。  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>設定及驗證委派

若要設定線上商務用 Skype，請遵循下列步驟：
  
### <a name="for-windows-clients"></a>適用于Windows用戶端

 **呼叫轉轉鍵**
  
1. 選取 **工具**  >  **選項**  >  **呼叫轉設定。**
    
2. 選取 **編輯我的代理人成員**。
    
3. 選取 **新增**，選取要新增的代理人， **然後選取確定**。
    
 **無呼叫轉轉鍵**
  
1. 在 Outlook中，**選取檔案**  >  **帳戶設定**  >  **委派 Access**  >  **Add**。
    
2. 找出並新增要成為代理人的人名。
    
3. 選取的 **日曆** 功能表，然後選取編輯器 (**可讀取、建立及修改) 。**
    
### <a name="for-mac-clients---lync"></a>Mac 用戶端 - Lync

 **呼叫轉轉鍵**
  
- 如果用戶端沒有具有編輯我的代理人成員連結的呼叫轉轉定位點，且委派程式位於 Mac 電腦上，則委派者必須登錄 Windows 型電腦，才能設定委派。 這是因為 Mac 用戶端無法建立 MAPI 連接，而這是從 商務用 Skype 建立Outlook。
    
### <a name="verify-success"></a>驗證成功

如果設定成功，代理人應該會看到您已新增為 < 名稱>的代理人訊息，以及已建立 "我 **管理** 通話的人 **"** 群組。 委派程式應該會看到已建立 **代理人** 群組。
  
> [!NOTE]
> 委派許可權通常會在設定程式 30 分鐘內顯示。 不過，此程式最多可能需要 24 小時才能完成。 
  
## <a name="troubleshooting"></a>疑難排解

### <a name="common-issues"></a>常見問題

- > **問題 1** 委派程式從用戶端移除代理人之後，代理人專案會繼續出現在我管理通話Outlook群組中。
    
  - > **解析度 1** 在 商務用 Skype用戶端上，以滑鼠右鍵按一下 [代理人群組中的代理人，然後選取 **[從群組移除**> 。
    
- > **問題 2** 透過用戶端授予代理人存取權Outlook，代理人不會顯示確認訊息或我 **管理** 通話的人群組。
    
  - > **解析度 2** 從用戶端移除Outlook，等待約 15 分鐘進行複製，然後再次新增代理人。
    
### <a name="other-common-issues"></a>其他常見問題

- 如果超過 25 個委派者與 25 個代理人的臨界值，則委派無法工作。
    
- 不支援 商務用 Skype基本用戶端。
    
    > [!NOTE]
    > 如果您安裝基本商務用 Skype，它會移除並中斷委派。 
  
- 如果 **MAPI 狀態** 值無法 **確定，** 請確認 SIP 和 **SMTP** 值相符。 
    
    > [!NOTE]
    > 當您第一次啟動 MAPI 狀態後，可能需要數分鐘的時間，才能顯示為確定商務用 Skype Outlook。
  
- 不支援為安全性群組建立安全性群組並新增委派許可權。
    
- MAPI 無法使用。 請參閱[2016 用戶端商務用 Skype MAPI 無法使用」錯誤](https://support.microsoft.com/help/3147130)。
    
- 無法Exchange Online用戶端來商務用 Skype信箱。 如果發生這種情況，請執行 Outlook[連接測試](https://testconnectivity.microsoft.com/)，以確保通過。
    
## <a name="related-topics"></a>相關主題
[設定商務用 Skype Online](set-up-skype-for-business-online.md)

[讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)

  
 
