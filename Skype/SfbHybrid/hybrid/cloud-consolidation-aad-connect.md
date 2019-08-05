---
title: 更新 AAD Connect 以包含一個以上的林
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 此附錄包含更新 AAD 連線的詳細步驟, 以包含多個林, 做為小組和商務用 Skype 的雲端整合的一部分。
ms.openlocfilehash: cbb4811d999601524557e7106840a66682565e5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185488"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="5bf54-103">更新 AAD Connect 以包含一個以上的林</span><span class="sxs-lookup"><span data-stu-id="5bf54-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="5bf54-104">Azure AD Connect 支援[從多個林進行同步](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies)處理。</span><span class="sxs-lookup"><span data-stu-id="5bf54-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="5bf54-105">不過, 它只支援 Azure AD Connect 同步處理到 AAD 的一個實例。</span><span class="sxs-lookup"><span data-stu-id="5bf54-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="5bf54-106">因此, 如果 Azure AD 已安裝在一個目錄林中, 則 AAD Connect 的現有實例必須更新, 才能從額外的林進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="5bf54-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="5bf54-107">如果所有身分識別都只會在兩個目錄林之間呈現一次, 您就可以直接重新執行 AAD 連接嚮導, 選擇 [自訂同步處理選項], 然後在 [連線**您的目錄]** 頁面上, 輸入其他林及憑據的名稱。</span><span class="sxs-lookup"><span data-stu-id="5bf54-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="5bf54-108">![[連線您的目錄] 頁面](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="5bf54-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="5bf54-109">不過, 如果使用者可以在多個目錄中存在, 而且您要合併資料 (例如, 如果連絡人物件存在於與另一個目錄林中的使用者對應的林中), 您將需要卸載 Azure AD Connect 並重新安裝。</span><span class="sxs-lookup"><span data-stu-id="5bf54-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="5bf54-110">這是因為跨目錄林連接規則條件只能在第一次安裝期間進行設定。</span><span class="sxs-lookup"><span data-stu-id="5bf54-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="5bf54-111">這會在下列頁面上完成:</span><span class="sxs-lookup"><span data-stu-id="5bf54-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="5bf54-112">![唯一識別您的使用者頁面](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="5bf54-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="5bf54-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="5bf54-113">See also</span></span>

[<span data-ttu-id="5bf54-114">團隊與商務用 Skype 的雲端整合</span><span class="sxs-lookup"><span data-stu-id="5bf54-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)