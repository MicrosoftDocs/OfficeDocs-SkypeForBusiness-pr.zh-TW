---
title: 安裝並測試適用于 Windows Phone 的商務用 Skype
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 54289bbe-97e7-44bf-8611-4e740fc5b998
description: 摘要：瞭解如何在 Windows Phone 上安裝及測試商務用 Skype。
ms.openlocfilehash: 8323231f67e8aca87d3670cfee1a2137f0dd6c21
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812713"
---
# <a name="install-and-test-skype-for-business-for-windows-phone"></a>安裝並測試適用于 Windows Phone 的商務用 Skype
 
**摘要：** 瞭解如何在 Windows Phone 上安裝及測試商務用 Skype。
  
商務用 Skype for Windows Phone 應用程式會將商務用 skype 狀態、立即訊息 (IM) ，以及語音和視頻呼叫傳送至 Windows mobile 裝置。 具有 Lync 2013 的使用者會自動取得更新的應用程式，或視使用者設定手動更新它。 新的使用者可以從 [Windows Phone Marketplace](https://go.microsoft.com/fwlink/p/?linkid=231901)下載。 Windows Phone 應用程式的商務用 Skype 只能在 Windows Phone 8.1 和更新版本上使用。
  
在您組織中的使用者下載應用程式之前，您會想要執行下列測試，以確定它已正確整合至您的環境。 
  
## <a name="install-skype-for-business-windows-phone-81"></a>安裝商務用 Skype Windows Phone 8。1

1. 流覽至 [Windows phone 8 更新中心](https://www.windowsphone.com/en-us/how-to/wp8/update-central) ，將您的手機更新為 Windows phone 8.1。
    
2. 在您的手機上，移至 [ **儲存**]，然後搜尋 **商務用 Skype**。
    
3. 按 [ **安裝**]。 
    
## <a name="sign-in-to-skype-for-business-for-the-first-time"></a>第一次登入商務用 Skype

1. 在 [ **開始** ] 畫面上，向左輕掃以查看已安裝的應用程式、搜尋商務用 Skype For Windows Phone，然後點擊圖示以開啟應用程式。
    
2. 輸入您的登入位址 (例如，user@domain.com) 和密碼，然後按一下 [ **完成**]。
    
     您可能會同時要求使用者名稱和登入位址。 使用者名稱是您用來登入組織網路的方式，可以是 user@domain.com 或網域 \ 使用者。
    
3. 在 [ **客戶經驗改進計畫** ] 畫面上，按一下 [ **加入** ]，將應用程式問題和使用方式的匿名資料傳送給 Microsoft，如果您不願意參與，請 **謝謝** 。
    
4. 在 [ **永不錯過您的工作來電** ] 畫面中，輸入您的行動電話號碼與國家/地區碼。 當 Windows Phone 的商務用 Skype 無法使用 Wi-Fi 或行動電話資料網路進行音訊或視頻通話時，系統會自動呼叫此號碼，並連接至通話的音訊部分。
    
5. 按 **[下一步]** 並複查通知和電話簿存取設定：
    
   - **推播通知** 當您收到新的 IM 或來電時，會收到警示。 通常 **在建議的) 上** (。
    
     > [!IMPORTANT]
     > 如果您關閉此設定，則除非該應用程式是作用中的，否則不會向 Im、來電或其他商務用 Skype for business 通知。 
  
   - **允許存取電話簿** 當您搜尋用於 Windows Phone 的商務用 Skype 中的連絡人時，搜尋行動電話上的連絡人。
    
6. 按 **[下一步]** 開始使用商務用 Skype For Windows Phone。
    
    [需要登入方面的協助嗎？](https://support.office.com/article/6b827683-ad55-471a-bd4b-3d4ec098bf75)
    
## <a name="verify-mobile-client-installation"></a>驗證行動用戶端安裝

在您設定用戶端並登入成功之後，請使用下列測試來確認您的行動裝置上安裝的 Windows 商務用 Skype Phone 是否正常運作。
  
### <a name="search-for-a-contact-in-the-corporate-directory"></a>在公司目錄中搜尋連絡人

1. 在 [連絡人] 清單中，按一下 [ **搜尋**]。
    
2. 搜尋只存在於全域通訊清單中的連絡人。
    
3. 確認連絡人名稱出現在搜尋結果中。
    
### <a name="test-instant-messaging-and-presence"></a>測試立即訊息和目前狀態

1. 在 [連絡人] 清單中，按一下連絡人。
    
2. 在連絡人卡片中，按一下立即訊息 (IM)  ![商務用 Skype 中的立即訊息圖示](../../media/90f8d5fa-7968-4ef7-bf5b-dddf9b893905.png)圖示。
    
3. 確認 IM 視窗隨即出現，而且您可以輸入並傳送 IM。
    
### <a name="test-dial-out-conferencing"></a>測試電話撥出式會議

1. 在 Outlook 中排程商務用 Skype 會議。
    
2. 在您的 Windows Phone 上，開啟會議邀請。
    
3. 按一下會議中的連結以加入。
    
4. 從會議服務接聽來電，並確認您已連線至會議音訊。
    
### <a name="test-push-notifications"></a>測試推播通知

1. 為此測試選取兩個不同的使用者帳戶。 
    
2. 在使用者 A 的 Windows Phone 上，使用使用者 A 的帳戶登入適用于 Windows Phone 的商務用 Skype。
    
3. 在裝置上開啟另一個應用程式。
    
4. 在不同的用戶端（例如桌面用戶端）上，使用使用者 B 的帳戶登入商務用 Skype。
    
5. 從使用者 B 傳送 IM 給使用者 A。
    
6. 確認 IM 通知出現在使用者 A 的行動裝置上。
    
## <a name="remove-skype-for-business-from-your-windows-phone"></a>從您的 Windows Phone 移除商務用 Skype

若要從行動裝置移除 Windows Phone 應用程式的商務用 Skype： 
  
1. 在 [開始] 畫面中，滑動以查看應用程式清單。 
    
2. 點選並按住商務用 Skype for Windows Phone 應用程式，然後選取 [ **卸載**]。
    


