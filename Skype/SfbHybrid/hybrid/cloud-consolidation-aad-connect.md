---
title: 更新 AAD 連線至包含多個樹系
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
description: 本附錄包含更新 AAD 連線至包含在多個樹系的 microsoft Teams 和商務用 Skype 雲端彙總的詳細的步驟。
ms.openlocfilehash: a61a45c8a492afd761f8cc6b1020b591851645b8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049095"
---
# <a name="update-aad-connect-to-include-more-than-one-forest"></a><span data-ttu-id="2658c-103">更新 AAD 連線至包含多個樹系</span><span class="sxs-lookup"><span data-stu-id="2658c-103">Update AAD Connect to include more than one forest</span></span>

<span data-ttu-id="2658c-104">Azure AD Connect 支援[多個樹系同步處理](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies)。</span><span class="sxs-lookup"><span data-stu-id="2658c-104">Azure AD Connect supports [syncing from multiple forests](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-topologies).</span></span> <span data-ttu-id="2658c-105">不過，它支援 Azure AD Connect 同步處理至 AAD 只能有一個執行的個體。</span><span class="sxs-lookup"><span data-stu-id="2658c-105">However, it supports only one instance of Azure AD Connect syncing to AAD.</span></span> <span data-ttu-id="2658c-106">因此，在 Azure AD 已安裝在一個樹系的情況下，AAD 連線的現有執行個體必須更新以從其他樹系的同步處理。</span><span class="sxs-lookup"><span data-stu-id="2658c-106">Therefore, in cases where Azure AD is already installed in one forest, the existing instance of AAD Connect must be updated to sync from the additional forest.</span></span>

 - <span data-ttu-id="2658c-107">如果這兩個樹系間只有一次表示所有的身分識別 （亦即，您還未做任何擁有郵件功能的連絡人），然後您可以只重新執行 [AAD 連線精靈]，選擇 [「 自訂同步處理選項 」，然後在 [**連線您的目錄**] 頁面中，輸入認證與其他樹系的名稱。</span><span class="sxs-lookup"><span data-stu-id="2658c-107">If all identities are represented only once across both forests (that is, you haven’t made any mail-enabled contacts), then you can simply re-run the AAD Connect wizard, choose “Customize synchronization options,” and then on the **Connect Your Directories** page, enter the name of the additional forest and creds.</span></span><br><br>
 <span data-ttu-id="2658c-108">![[連線目錄頁面](../media/cloud-consolidation-connect-your-directories.png)</span><span class="sxs-lookup"><span data-stu-id="2658c-108">![The Connect your directories page](../media/cloud-consolidation-connect-your-directories.png)</span></span>
 - <span data-ttu-id="2658c-109">不過，如果使用者可以在於超過一個目錄和您將會合併資料 （例如，如果連絡人物件對應至另一個樹系中的使用者樹系中有），則需要解除安裝 Azure AD Connect，並重新安裝它。</span><span class="sxs-lookup"><span data-stu-id="2658c-109">However, if users can exist in more than one directory and you’ll be merging the data (for example, if contact objects exist in a forest corresponding to users in another forest), you will need to uninstall Azure AD Connect and re-install it.</span></span>  <span data-ttu-id="2658c-110">這是因為只可以在第一個會安裝期間設定跨樹系聯結的規則條件。</span><span class="sxs-lookup"><span data-stu-id="2658c-110">This is because the cross-forest join rules condition can only be configured during the first install.</span></span> <span data-ttu-id="2658c-111">這是在下列頁面：</span><span class="sxs-lookup"><span data-stu-id="2658c-111">This is done on the following page:</span></span><br><br>
 <span data-ttu-id="2658c-112">![唯一識別您的使用者] 頁面](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span><span class="sxs-lookup"><span data-stu-id="2658c-112">![The Uniquely identifying your users page](../media/cloud-consolidation-uniquely-identifying-your-users.png)</span></span>


## <a name="see-also"></a><span data-ttu-id="2658c-113">請參閱</span><span class="sxs-lookup"><span data-stu-id="2658c-113">See also</span></span>

[<span data-ttu-id="2658c-114">針對小組與 Skype for Business 的雲端彙總</span><span class="sxs-lookup"><span data-stu-id="2658c-114">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)