---
title: 讓商務用 Skype 使用者新增 Skype 連絡人
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 08666236-1894-42ae-8846-e49232bbc460
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
- LIL_Placement
description: '瞭解如何讓使用商務用 Skype 的使用者從貴組織外的商務用 skype 連絡人，然後將他們新增至他們的連絡人清單。 '
ms.openlocfilehash: 71282fe105c85cadca9aab341fc1b5e6ffbe47d2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164472"
---
# <a name="let-skype-for-business-users-add-skype-contacts"></a>讓商務用 Skype 使用者新增 Skype 連絡人

在商務用 Skype 中，您的使用者可以在使用 Skype （免費應用程式）的所有人搜尋和傳送即時消息！ 本文說明您需要採取的動作，才能新增 Skype 連絡人。 
  
您必須在 Microsoft 365 或 Office 365 中擁有系統[管理員許可權](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d?ui=en-US&rs=en-US&ad=US)，才能執行此動作。

![商務用 Skype 標誌圖示](../images/sfb-logo-30x30.png) **使用商務用 Skype 系統管理中心**
  
1. 使用您的 Microsoft 365 或 Office 365 系統管理員帳戶登[https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home#/homepage)入。
    
2. 在系統管理中心中，移至 [系統**管理中心] 中心** > **商務用 Skype**。 
    
    ![選擇 [商務用 Skype 系統管理中心]。](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. 在 [商務用 Skype 系統管理中心]****，選擇 [組織]****  >  [外部通訊]****。 
    
4. 根據預設，您的使用者可以與使用商務用 Skype 的世界各地的其他人通訊（假設您的防火牆已設定為允許）。 
    
    ![選擇 [讓人員使用商務用 Skype 與 Skype 通訊]。](../images/333789f8-2ea6-4bbd-805b-18130f427999.png)
  
    如果您想要讓使用者與 Skype 使用者聊天，但不想讓他們與使用商務用 Skype 的其他人聊天，請選擇 [**僅針對允許的網域**]。 當您啟用與 Skype 使用者的聯絡時，系統會自動將 skype.com 新增為場景背後的允許網域。 
    
    如果您想要允許世界各地的其他企業使用商務用 Skype 與其他公司的聯絡，請選擇 [**封鎖的網域除外**]，然後選擇**+** 新增這些網域。 除了特定網域中的人員之外，所有人都能與您聯繫。 （有些公司可能會選擇此選項，例如，如果他們在訴訟中，而且需要確保與其他業務不一樣。）
    
5. 選擇 [**讓人員使用商務用 Skype 與組織外部的 skype 使用者通訊**]。 
    
6.  如果您使用的是 Windows 防火牆，商務用 Skype 會自動開啟所需的埠。
    
    如果您的組織使用另一個解決方案來限制您網路上的電腦連線至網際網路，請確定用戶端電腦能夠存取所有的[IP 位址和 url](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) ，瞭解 skype 連線與 Skype 目錄搜尋。 這可能需要將它們新增到防火牆或 proxy 基礎結構設定的輸出允許清單中。
    
7. 請**等候長達24小時進行測試**。 每當您變更 [外部通訊] 設定時，最多可能需要24小時才能在所有資料中心上填入變更。
    
8. 向您的使用者顯示如何尋找 Skype 連絡人並將其新增至其商務用 Skype 連絡人清單中。 指出他們[在商務用 Skype 中搜尋人員](https://support.office.com/article/b12500ef-e37f-4d22-aade-c11277e53f19)。
    
## <a name="test-and-troubleshoot"></a>測試和疑難排解

若要測試您的設定，您需要位於不在公司防火牆後的 Skype 上的連絡人。 他們可以使用 Gmail 帳戶、Outlook.com 帳戶或其他類型的電子郵件帳戶登入 Skype。
  
1. 在您變更 [外部通訊] 設定之後，請**等候長達24小時以進行測試**。
    
2. 登出商務用 Skype，然後再次登入，以查看搜尋 Skype 目錄的選項。 
    
    ![當 Skype 目錄醒目提示時，您可以搜尋擁有 Skype 帳戶的人員。](../images/76ee9fab-1ac3-4f4a-9569-f5f2606dbb7a.png)
  
3. 在商務用 Skype 中，搜尋您在 Skype 中的聯絡人，然後將要求傳送到聊天。 
    
    如果您收到由於公司原則而無法傳送的訊息，您必須仔細檢查您的[防火牆設定](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)。 
    
4. 測試問題是否是您的防火牆的另一種方法，就是移至不在防火牆背後的 wifi 位置（例如咖啡廳），並使用商務用 Skype 將要求傳送給您的 Skype 連絡人進行聊天。 
    
   - **如果您傳送給您的 Skype 聯絡人，且收件者沒有收到邀請**，請要求他們傳送聊天邀請。 如果問題是在 Skype 與商務用 Skype 之間建立連線，通常就是解決問題。
    
   - 現在，如果郵件是在咖啡廳，而不是在您工作時，您知道問題是您的防火牆。 
    
## <a name="what-you-can-and-cant-do"></a>您可以或不能執行的動作

- **Mac 版商務用 skype**無法搜尋及與 skype 連絡人進行通訊。
    
- 啟用 [目錄搜尋] 時，您可以搜尋並尋找 Skype 及商務用 Skype 使用者。 如果您由於某種原因無法搜尋目錄來找不到他們，您可以傳送連絡人要求，然後讓他們登入 Skype 並接受它，讓您可以與他們通訊。 
    
- 無法允許與其他 IM 供應商（例如 Google 或 Facebook）的 IM 連線。 您無法使用商務用 Skype 來傳送手機文字訊息。

- 無法錄製 Skype 連絡人與商務用 Skype 連絡人之間的音訊或視頻通話。
    
## <a name="what-features-are-available-when-adding-skype-contacts"></a>新增 Skype 連絡人時可使用哪些功能？

以 Microsoft 帳戶（先前稱為 Windows Live ID）登入的 Skype 連絡人在與您的商務用 Skype 使用者交談時，可以取得部分（但並非全部）功能。
  
|**適用于 Skype 連絡人**|**Skype 連絡人無法使用**|
|:-----|:-----|
| 影片交談 <br/>  人員對人立即訊息 <br/>  目前狀態 <br/> | 多方 IM 交談 <br/>  三人以上的音訊與影片交談 <br/>  桌面與程式共用 <br/> |
   
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>相關主題

[允許使用者連絡外部商務用 Skype 使用者](allow-users-to-contact-external-skype-for-business-users.md)
  
[設定商務用 Skype Online](set-up-skype-for-business-online.md)

  
 
