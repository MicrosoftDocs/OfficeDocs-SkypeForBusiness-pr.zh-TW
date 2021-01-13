---
title: Office 應用程式的商務用 Skype 相容性
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: 瞭解您可以從 Outlook 和其他 Microsoft Office 應用程式中存取商務用 Skype 功能的方式。
ms.openlocfilehash: b3d792d5e6376e4d845aa74f0585acf7d9a70d81
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802733"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Office 應用程式的商務用 Skype 相容性
 
瞭解您可以從 Outlook 和其他 Microsoft Office 應用程式中存取商務用 Skype 功能的方式。
  
本主題說明商務用 Skype 與各種版本的 Microsoft Office 套件的相容性。 
  
## <a name="office-and-skype-for-business"></a>Office 和商務用 Skype

下表說明 Office 的各個版本支援的商務用 Skype 功能：部署和整合 Exchange [隨商務用 Skype server 與 Exchange server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)所述。
  
**商務用 Skype 和 Microsoft Office 相容性**

|**功能**|**Microsoft Office 2010**|**Microsoft Office 2013、2015及2016**|**Mac 版 Office 2016** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook 功能** ||||
|自訂 Outlook 會議邀請 (新增徽標、協助 URL、免責聲明、頁腳文字)   |否  |是   |是|
|根據預設，設定會議選項以靜音出席者的音訊和影片    |否    |是    |否    |
|跨 Office 和商務用 Skype 管理連絡人清單的整合連絡人存放區    |否    |是 (需要 Exchange 2013 或更新版本)     |是    |
|高解析度設定檔圖片    |否    |是 (需要 Exchange 2013 或更新版本)     |是    |
|Microsoft Outlook [寄件者]、[收件者] 及 [抄送] 欄位中的目前狀態    |是    |是    |是    |
|使用 [可用性] 功能表中的 IM 或電話回復    |從連絡人卡片 (是)     |從連絡人卡片 (是)     |從連絡人卡片 (是)     |
|在 [排程助理] 索引標籤上的會議邀請中的目前狀態    |是    |是    |否    |
|使用接收的電子郵件訊息中的工具列或功能區回復 IM 或呼叫    |是    |是    |是    |
|**其他 Office 應用程式**   ||||
|OneNote 共用附注    |否    |是    |否    |
|安裝程式已整合至 Office 安裝程式    |否    |是    |否    |
|PowerPoint 簡報內容    |是    |是 (也可以使用 VBSS)     |是    |
|Microsoft Word 和 Microsoft Excel 檔案中的 IM 和目前狀態 (已啟用智慧標籤)     |僅限 Microsoft Word    |僅限 Microsoft Word    |否    |
|必須安裝 Outlook SharePoint 網站中的 IM 和目前狀態 (Outlook)     |是    |是    |否    |
   
&#x2776;-假設您已安裝，且目前正在執行 Mac 用戶端或 Lync 2011 for Mac 用戶端的商務用 Skype。
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server 和商務用 Skype

下表說明各種 Exchange Server 版本的商務用 Skype 支援。 必須在用戶端電腦上安裝 Outlook，才能處理延伸的 MAPI 呼叫，有些功能需要使用 Exchange Web 服務 (EWS) 。
  
**商務用 Skype 與 Exchange Server 的相容性**

|**Exchange Server 版本**|**商務用 Skype 支援**|
|:-----|:-----|
|Exchange Server 2019 (僅限商務用 Skype Server 2019)  |與 Exchange Server 2013 支援相同    |
|Exchange Server 2016    |與 Exchange Server 2013 支援相同  <br/> |
|Exchange Server 2013  <br/> |與 Exchange Server 2010 支援相同，加入  <br/>&bull;&nbsp;&nbsp;整合連絡人存放區  <br/>&bull;&nbsp;&nbsp;高解析度圖片  <br/>&bull;&nbsp;&nbsp;封存整合  <br/> **附注：** 如需詳細資訊，請參閱將 [商務用 Skype Server 與 Exchange Server 整合](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|Exchange Server 2010  <br/>僅 (商務用 Skype Server 2015)  |下列功能僅可透過 EWS:  <br/>&bull;&nbsp;&nbsp;讀取或刪除 [交談記錄] 資料夾中的專案  <br/>&bull;&nbsp;&nbsp;讀取或刪除語音信箱專案  <br/>&bull;&nbsp;&nbsp;顯示擴大的空閒/忙碌資訊和會議主旨和位置  <br/>&bull;&nbsp;&nbsp;Exchange 連絡人同步處理  <br/> 公用資料夾在 Exchange Server 2010 中是選用的。  <br/> |
   
## <a name="see-also"></a>另請參閱
 
[Windows 用戶端需求和軟體支援](windows-requirements.md)
  
[規劃會議用戶端 (Web 應用程式和會議應用程式) ](meetings-clients.md)

