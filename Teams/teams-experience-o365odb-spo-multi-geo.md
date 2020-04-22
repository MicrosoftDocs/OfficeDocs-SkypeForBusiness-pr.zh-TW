---
title: Microsoft 365 或 Office 365 OneDrive 與 SharePoint Online 多地域租賃中的團隊體驗
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: 瞭解如何在 Microsoft 365 或 Office 365 OneDrive 和 SharePoint Online 多地域租賃中使用團隊。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- SPO_Content
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 534155d49cda89291e5d8bdfb8da9b8caf0efb5f
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780392"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a><span data-ttu-id="99388-103">Microsoft 365 或 Office 365 OneDrive 與 SharePoint Online 多地域租賃中的團隊體驗</span><span class="sxs-lookup"><span data-stu-id="99388-103">Teams experience in a Microsoft 365 or Office 365 OneDrive and SharePoint Online Multi-Geo-enabled tenancy</span></span>
===========================================

<span data-ttu-id="99388-104">Microsoft 團隊是群組聊天軟體，也就是在 Office 365 中進行團隊合作的中心。</span><span class="sxs-lookup"><span data-stu-id="99388-104">Microsoft Teams is group chat software, the hub for teamwork in Office 365.</span></span> <span data-ttu-id="99388-105">它是由 Microsoft 365 群組服務以及 SharePoint Online 和商務用 OneDrive 提供給其檔案體驗所支援。</span><span class="sxs-lookup"><span data-stu-id="99388-105">It is powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="99388-106">在商務用 OneDrive/SharePoint Online 多地理租賃中，將租使用者延伸到許多地理位置（例如北美、歐洲和澳大利亞），基礎檔案體驗是多地區感知，所以小組使用檔案共同作業也是多地區的感知功能。</span><span class="sxs-lookup"><span data-stu-id="99388-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo aware, so the Teams experience with file collaboration is also Multi-Geo aware.</span></span> <span data-ttu-id="99388-107">這是團隊在其原生檔案體驗中跨多個 Geos 託管之程式的主要前沿功能。</span><span class="sxs-lookup"><span data-stu-id="99388-107">This is a key leading-edge capability for Teams to surface files hosted across multiple Geos in its native files experience.</span></span>

<span data-ttu-id="99388-108">例如，在 Contoso 租賃中，將歐洲作為衛星地理位置，而北美作為地理位置，但在左窗格中的 [檔案] 索引標籤下，歐元的附屬使用者將會看到他或她的 OneDrive 檔案，不過這些檔案是託管在歐洲資料位置，而美國是租使用者的中心位置。</span><span class="sxs-lookup"><span data-stu-id="99388-108">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see his or her OneDrive files under the Files tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="99388-109">此外，使用者也可以在最近的 [查看] 薄片下存取最近使用過的檔案。</span><span class="sxs-lookup"><span data-stu-id="99388-109">Also, the user can access the most recently used files under the Recent view blade.</span></span> <span data-ttu-id="99388-110">[最近的檔案] 可能包含使用者與其他 Geos 中的使用者共用的檔案，而且可能是受租使用者延伸的其他地理位置。</span><span class="sxs-lookup"><span data-stu-id="99388-110">Recent files may include files shared with the user from users in other Geos and might be mastered in other Geo locations that the tenant is extended to.</span></span> 

<span data-ttu-id="99388-111">指定團隊的群組網站也是多地區感知功能。</span><span class="sxs-lookup"><span data-stu-id="99388-111">A given Team’s group site is also Multi-Geo aware.</span></span> <span data-ttu-id="99388-112">也就是說，如果歐洲的附屬使用者正在建立小組，則會在歐洲位置建立對應的群組網站，而與該小組群組相關聯的檔案將會保留在該位置。</span><span class="sxs-lookup"><span data-stu-id="99388-112">That is, if a European satellite user is creating a Team, the corresponding Groups site will be created in the Europe location and the files associated with that Team group will be kept at rest in that location.</span></span> <span data-ttu-id="99388-113">任何後續的體驗（例如上傳新檔案或編輯檔案）都將針對該歐洲位置，以保證資料在這些檔案中保持常駐。</span><span class="sxs-lookup"><span data-stu-id="99388-113">Any subsequent experiences, such as uploading a new file or editing the file, will be targeted to that European location, keeping the promise of data residency for those files.</span></span> <span data-ttu-id="99388-114">如此一來，基本的基礎 Microsoft 365 群組就能成為多地區感知，這一切都有可能完成。</span><span class="sxs-lookup"><span data-stu-id="99388-114">This is all made possible by the underlying foundation Microsoft 365 Groups becoming Multi-Geo aware.</span></span>

<span data-ttu-id="99388-115">因為多地域租賃是單一全域租使用者，所以在 @ 提及中，衛星使用者將能夠在全球各地查看其同事，無論其位於何處。</span><span class="sxs-lookup"><span data-stu-id="99388-115">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they reside.</span></span> 

<span data-ttu-id="99388-116">請注意，小組體驗中的聊天與會議 IM 筆記中的交談並不是多地區感知，而且都只會保留在租使用者的中央位置。</span><span class="sxs-lookup"><span data-stu-id="99388-116">Note that conversations in chats and meeting IM notes within the Teams experience are not Multi-Geo aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="99388-117">通常，聊天交談不會套用至資料派駐需求。</span><span class="sxs-lookup"><span data-stu-id="99388-117">Typically, chat conversations aren’t applied to data residency needs.</span></span>

<span data-ttu-id="99388-118">如需 Office 365 多地理位置的詳細資訊，請參閱[Microsoft 多地區功能頁面](https://aka.ms/multi-geo)。</span><span class="sxs-lookup"><span data-stu-id="99388-118">For more information about Office 365 Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>