---
title: 在 Microsoft 365 多地域環境中的團隊體驗
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
ms.custom: seo-marvel-apr2020
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
description: 在本文中，您將學習如何在 Microsoft 365 多地區啟用的環境中使用團隊。
ms.openlocfilehash: 1a1689d78f6ce4e35b2e632e4a46ff0ec23a0d15
ms.sourcegitcommit: 7575fb476a594d70084c603e508dd311ef1d7edb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/05/2021
ms.locfileid: "49757748"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="5d319-103">在 Microsoft 365 多地域租賃中的團隊體驗</span><span class="sxs-lookup"><span data-stu-id="5d319-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="5d319-104">Microsoft 團隊是群組聊天軟體，即在 Microsoft 365 中進行團隊合作的中心。</span><span class="sxs-lookup"><span data-stu-id="5d319-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365.</span></span> <span data-ttu-id="5d319-105">它由 Microsoft 365 群組服務提供支援，以及 SharePoint 和 OneDrive 的檔案體驗。</span><span class="sxs-lookup"><span data-stu-id="5d319-105">It is powered by the Microsoft 365 Groups service along with SharePoint and OneDrive for its files experience.</span></span> <span data-ttu-id="5d319-106">在已將租使用者延伸至多個地理位置（例如北美、歐洲和澳大利亞）的多地域組織中，基本的檔案體驗是多地區感知，所以小組使用檔案共同作業也能感知多地區。</span><span class="sxs-lookup"><span data-stu-id="5d319-106">In a Multi-Geo organization in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="5d319-107">這可讓團隊在其原生檔案體驗中跨多個地理位置託管的 surface 檔。</span><span class="sxs-lookup"><span data-stu-id="5d319-107">This allows Teams to surface files hosted across multiple geo locations in its native files experience.</span></span>

<span data-ttu-id="5d319-108">例如，在 Contoso 租賃中，將歐洲作為衛星地理位置，而北美作為地理位置，但在左窗格中的 [檔案] 索引標籤下，歐元的附屬使用者將會看到他或她的 OneDrive 檔案，不過這些檔案是託管在歐洲資料位置，而美國是租使用者的中心位置。</span><span class="sxs-lookup"><span data-stu-id="5d319-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="5d319-109">此外，使用者也可以在最近的 [查看] 薄片下存取最近使用過的檔案。</span><span class="sxs-lookup"><span data-stu-id="5d319-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="5d319-110">[最近的檔案] 可能包含從其他地域位置中的使用者共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="5d319-110">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="5d319-111">指定的小組的 SharePoint 網站也是多地區感知功能。</span><span class="sxs-lookup"><span data-stu-id="5d319-111">A given Team’s SharePoint site is also Multi-Geo aware.</span></span> <span data-ttu-id="5d319-112">也就是說，如果歐洲的附屬使用者正在建立小組，則會在歐洲位置建立對應的 SharePoint 網站，並將與該小組相關聯的檔案保留在該位置。</span><span class="sxs-lookup"><span data-stu-id="5d319-112">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location and the files associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="5d319-113">任何後續的體驗（例如上傳新檔案或編輯檔案）都將儲存在該歐洲位置，以保證資料在這些檔案中保持常駐。</span><span class="sxs-lookup"><span data-stu-id="5d319-113">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="5d319-114">請注意，小組體驗中的聊天與會議 IM 筆記中的交談並不是多地區感知，而且都只會保留在組織的中央位置。</span><span class="sxs-lookup"><span data-stu-id="5d319-114">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the organization.</span></span>

<span data-ttu-id="5d319-115">如需多地理位置的詳細資訊，請參閱 [Microsoft 多地區功能](https://aka.ms/multi-geo)。</span><span class="sxs-lookup"><span data-stu-id="5d319-115">For more information about Multi-Geo, see [Microsoft Multi-Geo capabilities](https://aka.ms/multi-geo).</span></span>
