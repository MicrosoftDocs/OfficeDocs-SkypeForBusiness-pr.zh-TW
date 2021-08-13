---
title: 在移轉後變更簡單 URL
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 商務用 Skype Server 支援簡易 URLs。
ms.openlocfilehash: c3d78387ae0bcf16204e2fcaa4ff7db3549334fe814a014a88c80e8ab6658d5b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324722"
---
# <a name="change-simple-urls-after-migration"></a>在移轉後變更簡單 URL

商務用 Skype Server 支援三種簡單的 URLs：
  
- 「**開會**」是網站或組織中所有會議的基礎 URL。 使用符合簡易 URL 時，加入會議的連結就很容易理解，而且易於進行通訊和發佈。 
    
- **撥入功能** 可讓您存取電話撥入式會議設定網頁。 撥入簡易 URL 會包含在所有會議邀請中，讓想要撥入會議的使用者可以存取必要的電話號碼和 PIN 碼資訊。 
    
- 系統 **管理員** 可讓您快速存取商務用 Skype Server 控制台。 系統管理員簡易 URL 是您組織內部。 
    
在遷移至商務用 Skype Server 後，您必須注意變更會如何影響您的 DNS 記錄和憑證，以用於簡易 URLs。 如果舊版的商務用 Skype Server Director 在拓撲中仍在使用中，則不需要對您的簡單 URLs 進行任何變更。 如果在遷移之後從拓撲中移除商務用 Skype Server Director，則必須更新簡單 URL 的 DNS 記錄，以指向其中一個商務用 Skype Server 集區。 不過，每當您變更簡易 URL 名稱時，您必須在每個 Director 和前端伺服器上執行 Enable-CsComputer，以註冊變更。

## <a name="to-update-the-meet-simple-url"></a>更新符合簡易 URL

1. 在 [拓撲產生器] 中，以滑鼠右鍵按一下上方節點 **商務用 Skype Server**，然後按一下 [**編輯屬性**]。
    
2. 在左窗格中選取 [ **簡單 URLs** ]，然後在 [ **會議 URLs：** 選取 [符合 url]，然後按一下 [ **編輯 URL**]。
    
3. 將 URL 更新為想要的值，然後按一下 **[確定]** 儲存編輯的 URL。 
    
## <a name="to-update-the-admin-simple-url"></a>更新系統管理員簡易 URL

1. 在 [拓撲產生器] 中，以滑鼠右鍵按一下上方節點 **商務用 Skype Server**，然後按一下 [**編輯屬性**]。
    
2. 在左窗格中選取 [**簡單 URLs** ]，然後在 [系統 **管理存取 URL** ] 方塊中，輸入您要用於管理存取商務用 Skype Server 控制台的簡易 URL，然後按一下 **[確定]**。
    
   > [!TIP]
   > 建議您盡可能使用最簡單的 URL 作為 Admin URL。 最簡單的選項是 https://admin ... <em>\<domain\></em> 
  
## <a name="see-also"></a>另請參閱

[商務用 Skype Server 中簡易 URLs 的 DNS 需求](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
