---
title: 更新 AAD Connect 以包含多個樹系
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
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本附錄包含更新 AAD 連線的詳細步驟，以包含多個樹系，作為小組和商務用 Skype 的雲端合併的一部分。
ms.openlocfilehash: 19b761f3b64caf7afad7d37a51ae391e23d6b5ef
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120372"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="86161-103">更新 AAD Connect 以包含多個樹系</span><span class="sxs-lookup"><span data-stu-id="86161-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="86161-104">Azure AD Connect 支援 [從多個樹系進行同步](/azure/active-directory/connect/active-directory-aadconnect-topologies)處理。</span><span class="sxs-lookup"><span data-stu-id="86161-104">Azure AD Connect supports [syncing from multiple forests](/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="86161-105">不過，它只支援 Azure AD Connect 的一個實例同步至 AAD。</span><span class="sxs-lookup"><span data-stu-id="86161-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="86161-106">因此，在 Azure AD 已安裝在一個樹系中的情況下，必須更新 AAD 連線的現有實例，以便從其他樹系進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="86161-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="86161-107">若所有的身分識別只會在兩個樹系中呈現一次 (也就是說，您未將任何擁有郵件功能的連絡人) 上，請選擇 [自訂同步處理選項]，然後在 [連線您的 **目錄** ] 頁面上，輸入其他樹系和身分識別的名稱。</span><span class="sxs-lookup"><span data-stu-id="86161-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="86161-108">![[連線您的目錄] 頁面](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="86161-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="86161-109">不過，如果使用者可以存在於多個目錄中，且您將會合並資料 (例如，如果連絡人物件存在於與另一個樹系中的使用者相對應的樹系) 中，您將需要卸載 Azure AD Connect，然後重新安裝。</span><span class="sxs-lookup"><span data-stu-id="86161-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="86161-110">這是因為跨樹系的加入規則條件只會在第一次安裝期間進行設定。</span><span class="sxs-lookup"><span data-stu-id="86161-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="86161-111">這是在下列頁面上完成：</span><span class="sxs-lookup"><span data-stu-id="86161-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="86161-112">![唯一識別使用者頁面](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="86161-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="86161-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="86161-113">See also</span></span>

[<span data-ttu-id="86161-114">小組和商務用 Skype 的雲端整合</span><span class="sxs-lookup"><span data-stu-id="86161-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)