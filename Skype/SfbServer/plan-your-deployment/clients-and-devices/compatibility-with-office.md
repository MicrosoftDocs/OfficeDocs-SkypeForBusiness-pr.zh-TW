---
title: 商務用 Skype 與 Office 應用程式的相容性
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: 瞭解您可以從 Outlook 和其他 Microsoft Office 應用程式存取商務用 Skype 功能的方式。
ms.openlocfilehash: c24c6b08e21db357d52b1cc130e53f23b6123ff6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187897"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>商務用 Skype 與 Office 應用程式的相容性
 
瞭解您可以從 Outlook 和其他 Microsoft Office 應用程式存取商務用 Skype 功能的方式。
  
本主題說明商務用 Skype 與各種版本的 Microsoft Office 套件的相容性。 
  
## <a name="office-and-skype-for-business"></a>Office 和商務用 Skype

下表說明在部署 Exchange 之後, 各個版本的 Office 支援的商務用 Skype 功能, 如將[商務用 Skype 伺服器與 Exchange Server 整合在一起](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)所述。
  
**商務用 Skype 和 Microsoft Office 相容性**

|**功能**|**Microsoft Office 2010**|**Microsoft Office 2013、2015和2016**|**Mac 版 Office 2016** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook 功能** ||||
|自訂 Outlook 會議邀請 (新增標誌、說明 URL、免責聲明、頁尾文字)  |不  |是的   |是的|
|[設定會議] 選項預設會將出席者的音訊和影片設為靜音    |不    |是的    |不    |
|在 Office 和商務用 Skype 中管理連絡人清單的整合連絡人存放區    |不    |是 (需要 Exchange 2013 或更新版本)    |是的    |
|高解析度個人資料圖片    |不    |是 (需要 Exchange 2013 或更新版本)    |是的    |
|Microsoft Outlook [寄件者]、[收件者] 和 [抄送] 欄位    |是的    |是的    |是的    |
|從 [可用性] 功能表回復 [IM] 或 [通話]    |[是] (從連絡人卡片)    |[是] (從連絡人卡片)    |[是] (從連絡人卡片)    |
|[排程小幫手] 索引標籤上會議邀請中的目前狀態    |是的    |是的    |不    |
|透過接收到的電子郵件訊息中的工具列或功能區中的 IM 或呼叫回復    |是的    |是的    |是的    |
|**其他 Office 應用程式**   ||||
|OneNote 共用筆記    |不    |是的    |不    |
|集成至 Office 安裝程式的設定    |不    |是的    |不    |
|PowerPoint 簡報內容    |是的    |是 (VBSS 也有提供)    |是的    |
|Microsoft Word 和 Microsoft Excel 檔案中的 IM 和目前狀態 (啟用智慧標籤)    |僅限 Microsoft Word    |僅限 Microsoft Word    |不    |
|Microsoft SharePoint 網站中的 IM 和目前狀態 (必須安裝 Outlook)    |是的    |是的    |不    |
   
&#x2776;-假設您已安裝, 且目前正在執行 Mac 版商務用 Skype, 或 Mac 版 Lync 2011 用戶端。
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server 和商務用 Skype

下表說明各種 Exchange 伺服器版本的商務用 Skype 支援。 Outlook 必須安裝在用戶端電腦上, 才能處理延伸的 MAPI 呼叫, 而某些功能則需要使用 Exchange Web 服務 (EWS)。
  
**商務用 Skype 與 Exchange Server 相容性**

|**Exchange Server 版本**|**商務用 Skype 支援**|
|:-----|:-----|
|Exchange Server 2019 (僅適用于商務用 Skype Server 2019) |與 Exchange Server 2013 支援相同    |
|Exchange Server 2016    |與 Exchange Server 2013 支援相同  <br/> |
|Exchange Server 2013  <br/> |與 Exchange Server 2010 支援相同, 增加  <br/>&bull;&nbsp;&nbsp;整合連絡人存放區  <br/>&bull;&nbsp;&nbsp;高解析度圖片  <br/>&bull;&nbsp;&nbsp;存檔整合  <br/> **注意:** 如需詳細資訊, 請參閱將[商務用 Skype 伺服器與 Exchange Server 整合](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|Exchange Server 2010  <br/>(僅適用于商務用 Skype Server 2015) |下列功能只能透過 EWS 使用:  <br/>&bull;&nbsp;&nbsp;讀取或刪除 [交談記錄] 資料夾中的專案  <br/>&bull;&nbsp;&nbsp;讀取或刪除語音信箱專案  <br/>&bull;&nbsp;&nbsp;顯示延伸的空閒/忙碌資訊及會議主旨和位置  <br/>&bull;&nbsp;&nbsp;Exchange 連絡人同步處理  <br/> 公用資料夾在 Exchange Server 2010 中是選用的。  <br/> |
   
## <a name="see-also"></a>另請參閱
 
[Windows 用戶端需求與軟體支援](windows-requirements.md)
  
[規劃會議用戶端 (Web App 與會議應用程式)](meetings-clients.md)

