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
description: 本文說明如何設定和疑難排解商務用 Skype Online 委派。 本文提供設定建議、最佳做法及疑難排解步驟的指導方針。
ms.openlocfilehash: fac2b68deec94825d57fd06b436d00feaa924a5c
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706478"
---
# <a name="set-up-and-troubleshoot-skype-for-business-online-delegation"></a>商務用 Skype Online 委派的設定和疑難排解

本文說明如何設定和疑難排解商務用 Skype Online 委派。 本文提供設定建議、最佳做法及疑難排解步驟的指導方針。
  
## <a name="guidelines-and-requirements"></a>原則與需求

### <a name="guidelines-for-delegation"></a>委派指導方針

設定和取得委派正常運作的方式，取決於您遵循下列指導方針：
  
- 您必須使用商務用 Skype 2015 完整版用戶端（含最新的更新或商務用 Skype 2016 完整用戶端）。
    
- 您必須使用 Outlook 2013 用戶端，並安裝最新的更新或 Outlook 2016 用戶端。
    
- 確定 delegator 和委派電腦有一個作為主要或預設設定檔的 Outlook 郵件設定檔。 該郵件設定檔應該只包含一個帳戶。
    
- Delegator 和代理人的商務用 Skype 應該是線上使用者。 此外，每個帳戶的 Exchange 伺服器信箱都必須是線上或都在內部部署。
    
- Delegator 和代理人都應該使用相同的主要版本的 Outlook。
    
- 在用戶端原則中， **EnableExchangeDelegateSync**屬性值應該設定為**true** 。 您可以在商務用 Skype Online PowerShell 模組中執行**CSClientPolicy** Cmdlet，以驗證此設定。
    
- 在不同的工作站上，delegator 和代理人都必須登入商務用 Skype 和 Outlook。
    
- 商務用 Skype Online 委派不支援共用信箱。 這是因為共用信箱沒有**sendonbehalf**存取控制清單（ACL）。
    
### <a name="skype-for-business-client-version-support"></a>商務用 Skype 用戶端版本支援

||**Outlook 2013**|**Outlook 2016**|
|:-----|:-----|:-----|
|**Lync/商務用 Skype 基本用戶端**| 不支援 |不支援
|**商務用 Skype 2015**|受| 受|
|**商務用 Skype 2016**|受| 受|

   
### <a name="licensing-requirements"></a>授權需求

**企業版 E3 授權案例**

|**授權**|**台**|**筆記**|
|:-----|:-----|:-----|
|企業版 E3  <br/> |Lync 2013 （商務用 Skype 2015）與 Outlook 2013 或 Outlook 2016 搭配使用  <br/> 與 Outlook 2013 或 Outlook 2016 搭配使用的商務用 Skype 2016  <br/> |商務用 Skype 基本用戶端不支援委派。  <br/> 對於 Mac 用戶端，您可以委派通話，但不能委派會議。  <br/> |
|企業版 E3 （含 Office 365 電話系統 + Office 365 xCalling 方案）  <br/> |Lync 2013 （商務用 Skype 2015）與 Outlook 2013 或 Outlook 2016 搭配使用  <br/> 與 Outlook 2013 或 Outlook 2016 搭配使用的商務用 Skype 2016  <br/> Lync for Mac 2011  <br/> |商務用 Skype 基本用戶端不支援委派。  <br/> 對於 Mac 用戶端，您可以委派通話，但不能委派會議。  <br/> |
   
**企業版 E5 授權案例**

|**授權**|**台**|**筆記**|
|:-----|:-----|:-----|
|企業版 E5  <br/> |Lync 2013 （商務用 Skype 2015）與 Outlook 2013 或 Outlook 2016 搭配使用。  <br/> 與 Outlook 2013 或 Outlook 2016 搭配使用的商務用 Skype 2016  <br/> |商務用 Skype 基本用戶端不支援委派。  <br/> 對於 Mac 用戶端，您可以委派通話，但不能委派會議。  <br/> |
|企業版 E5 加上 Office 365 通話方案  <br/> |Mac 版商務用 Skype 2016  <br/> Lync 2013 （商務用 Skype 2015）與 Outlook 2013 或 Outlook 2016 搭配使用  <br/> 與 Outlook 2013 或 Outlook 2016 搭配使用的商務用 Skype 2016  <br/> Lync for Mac 2011  <br/> |商務用 Skype 基本用戶端不支援委派。  <br/> 對於 Mac 用戶端，您可以委派通話，但不能委派會議。  <br/> |
   
## <a name="set-up-and-verify-delegation"></a>設定並驗證委派

若要設定商務用 Skype Online 委派，請遵循下列步驟：
  
### <a name="for-windows-clients"></a>針對 Windows 用戶端

 **[來電轉接] 索引標籤**
  
1. 選取 [**來電轉接設定**] 的 [**工具** > **選項** > ]。
    
2. 選取 [**編輯我的代理人成員**]。
    
3. 選取 [**新增**]，選取您要新增的代理人，然後選取 **[確定]**。
    
 **[無來電轉接] 索引標籤**
  
1. 在 Outlook 中，**選取** > [檔案**帳戶設定** > **] 委派 Access** > [**新增**]。
    
2. 找出並新增要成為代理人的人員名稱。
    
3. 選取 [行事**曆**] 功能表，然後選取 **[編輯者（可讀取、建立及修改專案）**]。
    
### <a name="for-mac-clients---lync"></a>針對 Mac 用戶端-Lync

 **[來電轉接] 索引標籤**
  
- 如果用戶端沒有 [**編輯我的代理人成員**] 連結的 [**來電轉接**] 索引標籤，且 delegator 位於 Mac 電腦上，Delegator 必須登入 Windows 電腦，才能設定委派。 這是因為 Mac 用戶端無法進行 MAPI 連線，而這是從 Outlook 建立商務用 Skype 委派所需要的。
    
### <a name="verify-success"></a>驗證成功

如果設定成功，代理人會看到**您已新增為 < 名稱>** 訊息的代理人，也會建立 [**我管理的人員**] 群組通話。 Delegator 應該會看到 [**代理人**] 群組已建立。
  
> [!NOTE]
> 委派許可權通常會出現在安裝程式的30分鐘內。 不過，這個處理常式可能需要長達24小時才能完成。 
  
## <a name="troubleshooting"></a>疑難排解

### <a name="common-issues"></a>常見問題

- > **問題 1**在 delegator 已移除 Outlook 用戶端的代理人之後，該代理人專案會繼續出現在 [**我管理呼叫**] 群組的 [人員]。
    
  - > **解析度 1**在商務用 Skype 用戶端上，以滑鼠右鍵按一下 [**代理人**] 群組中的代理人，然後選取 [**從群組移除**]。
    
- > **問題 2**透過 Outlook 用戶端授與委派存取權之後，就不會再顯示確認訊息，也不會顯示 [**我管理的使用者**] 群組通話的人員。
    
  - > **解析度 2**移除 Outlook 用戶端的委派，等待大約15分鐘進行複製，然後再新增該代理程式。
    
### <a name="other-common-issues"></a>其他常見問題

- 如果超過25個 delegators 及25個代理人的閾值，委派就無法運作。
    
- 商務用 Skype 基本用戶端不受支援。
    
    > [!NOTE]
    > 如果您安裝商務用 Skype 基本用戶端，則會移除並中斷委派。 
  
- 如果**MAPI 狀態值**不是 **[確定]**，請確定**SIP**與**SMTP**值相符。
    
    > [!NOTE]
    > 在您第一次啟動商務用 Skype 和 Outlook 之後，可能需要幾分鐘的時間，才能讓 MAPI 狀態顯示為 **[確定]** 。
  
- 不支援建立安全性群組及新增該安全性群組的委派許可權。
    
- MAPI 無法使用。 請參閱[商務用 Skype 2016 用戶端的「MAPI 無法使用」錯誤](https://support.microsoft.com/en-us/help/3147130)。
    
- 無法透過商務用 Skype 用戶端存取 Exchange Online 信箱。 如果發生這種情況，請執行[Outlook 連線測試](https://testconnectivity.microsoft.com/)，以確定它已通過。
    
## <a name="related-topics"></a>相關主題
[設定商務用 Skype Online](set-up-skype-for-business-online.md)

[讓商務用 Skype 使用者新增 Skype 連絡人](let-skype-for-business-users-add-skype-contacts.md)

  
 
