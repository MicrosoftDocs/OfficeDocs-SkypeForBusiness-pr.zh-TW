---
title: 遷移後變更簡單的 Url
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 商務用 Skype 伺服器支援簡單的 Url。
ms.openlocfilehash: 786e3f5d7ed273c0f3c2ccc39ef1b539714de61b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193078"
---
# <a name="change-simple-urls-after-migration"></a>遷移後變更簡單的 Url

商務用 Skype 伺服器支援三個簡單的 Url:
  
- [**開會**] 是用來做為網站或組織中所有會議的基底 URL。 使用 [符合簡單的 URL], 加入會議的連結就很容易理解, 且易於溝通及發佈。 
    
- [**撥**入] 可讓您存取 [電話撥入式會議] 設定網頁。 [撥入] 簡單 URL 包含在所有會議邀請中, 讓想要撥入會議的使用者可以存取必要的電話號碼和 PIN 資訊。 
    
- [系統**管理**] 可讓您快速存取商務用 Skype Server 的 [控制台]。 系統管理員簡易 URL 是貴組織的內部。 
    
遷移到商務用 Skype Server 之後, 您必須知道變更對您的 DNS 記錄及簡單 Url 的憑證有何影響。 如果舊版商務用 Skype Server 主管在拓撲中保持使用, 則不需要變更您的簡單 Url。 如果在遷移之後從拓撲中移除商務用 Skype Server 主管, 則必須更新簡單的 URL DNS 記錄, 以指向其中一個商務用 Skype 伺服器池。 不過, 每當您變更簡單的 URL 名稱時, 您必須在每個控制器和前端伺服器上執行 Enable-CsComputer, 以登錄變更。

## <a name="to-update-the-meet-simple-url"></a>若要更新 [符合簡單 URL]

1. 在拓撲建立器中, 以滑鼠右鍵按一下**商務用 Skype 伺服器**的頂端節點, 然後按一下 [**編輯屬性**]。
    
2. 選取左窗格中的 [**簡單 url** ], 然後選取 [**會議 url]:** 選取 [認識 url], 然後按一下 [**編輯 URL**]。
    
3. 更新 URL 至您想要的值, 然後按一下 **[確定]** 以儲存編輯的 URL。 
    
## <a name="to-update-the-admin-simple-url"></a>更新管理員簡易 URL

1. 在拓撲建立器中, 以滑鼠右鍵按一下**商務用 Skype 伺服器**的頂端節點, 然後按一下 [**編輯屬性**]。
    
2. 選取左窗格中的 [**簡單 url** ], 然後在 [**管理存取 URL** ] 方塊中, 輸入您要用來管理商務用 Skype Server [控制台] 的簡單 URL, 然後按一下 **[確定]**。
    
   > [!TIP]
   > 我們建議您使用最簡單的管理 URL URL。 最簡單的選項https://admin就是。<em> \<網域\></em>。 
  
## <a name="see-also"></a>另請參閱

[商務用 Skype Server 中簡單 Url 的 DNS 需求](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
