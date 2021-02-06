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
description: 在本文中，您將學習如何在 Microsoft 365 多地域環境中使用團隊。
ms.openlocfilehash: 43abe221c6159e6dfed1705f5cbc4839c1ce57db
ms.sourcegitcommit: 93d84e172cb4b19acde4b8bae9b77efe96c44c00
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122243"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a><span data-ttu-id="ee3f7-103">在 Microsoft 365 多地域租賃中的團隊體驗</span><span class="sxs-lookup"><span data-stu-id="ee3f7-103">Teams experience in a Microsoft 365 Multi-Geo-enabled tenancy</span></span>

<span data-ttu-id="ee3f7-104">Microsoft 團隊是群組聊天軟體，即在 Microsoft 365 和 Office 365 中進行團隊合作的中心。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-104">Microsoft Teams is group chat software, the hub for teamwork in Microsoft 365 and Office 365.</span></span> <span data-ttu-id="ee3f7-105">它是由 Microsoft 365 群組服務以及 SharePoint Online 和商務用 OneDrive 提供給其檔案體驗所支援。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-105">It's powered by the Microsoft 365 Groups service along with SharePoint Online and OneDrive for Business for its files experience.</span></span> <span data-ttu-id="ee3f7-106">在商務用 OneDrive/SharePoint Online 多地理租賃中，將租使用者延伸至多個地理位置（例如北美、歐洲和澳大利亞），基礎檔案體驗是多地區感知，所以小組使用檔案共同作業也是多地區感知。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-106">In a OneDrive for Business/SharePoint Online Multi-Geo tenancy, in which the tenant is extended to many geographic locations such as North America, Europe, and Australia, the underlying files experience is Multi-Geo-aware, so the Teams experience with file collaboration is also Multi-Geo-aware.</span></span> <span data-ttu-id="ee3f7-107">此功能是小組的主要主要功能，可供團隊在其原生檔案體驗中跨多個 Geos 託管的檔案。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-107">This functionality is a key leading-edge capability for Teams to surface files that are hosted across multiple Geos in its native files experience.</span></span> <span data-ttu-id="ee3f7-108">這也包括 OneNote 和 Wiki 檔案。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-108">This also includes OneNote and Wiki files.</span></span>

<span data-ttu-id="ee3f7-109">例如，在 Contoso 租賃中，將歐洲作為衛星地理位置，而北美是中央地理位置，但在左窗格中的 [檔案] 索引標籤底下， **歐洲的使用者** 將會看到他們的 OneDrive 檔案，但檔案是託管在歐洲資料位置，而美國是租使用者的中央位置。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-109">For example, in a Contoso tenancy with Europe as a satellite Geo and North America as the central Geo, a European satellite user will see their OneDrive files under the **Files** tab in left pane, although the files are hosted in the Europe data location and the United States is the tenant’s central location.</span></span> <span data-ttu-id="ee3f7-110">此外，使用者也可以在 **最近** 的 [查看] 薄片下存取最近使用過的檔案。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-110">Also, the user can access the most recently used files under the **Recent** view blade.</span></span> <span data-ttu-id="ee3f7-111">[最近的檔案] 可能包含從其他地域位置中的使用者共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-111">Recent files may include files shared from users in other geo locations.</span></span> 

<span data-ttu-id="ee3f7-112">指定團隊的 SharePoint 網站也是多地區感知。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-112">A given Team’s SharePoint site is also Multi-Geo-aware.</span></span> <span data-ttu-id="ee3f7-113">也就是說，如果歐洲的附屬使用者正在建立小組，則會在歐洲位置建立對應的 SharePoint 網站。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-113">That is, if a European satellite user is creating a Team, the corresponding SharePoint site will be created in the Europe location.</span></span> <span data-ttu-id="ee3f7-114">與該小組相關聯的檔案會保留在該位置的其他檔案中。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-114">The files that are associated with that Team will be kept at rest in that location.</span></span> <span data-ttu-id="ee3f7-115">任何後續的體驗（例如上傳新檔案或編輯檔案）都將儲存在該歐洲位置，以保證資料在這些檔案中保持常駐。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-115">Any subsequent experiences, such as uploading a new file or editing the file, will be stored in that European location, keeping the promise of data residency for those files.</span></span>

<span data-ttu-id="ee3f7-116">因為多地域租賃是單一全域租使用者，所以在 @ 提及中，衛星使用者將能夠在全球各地查看其同事，不論他們身在何處。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-116">Because a Multi-Geo tenancy is a single global tenant, during @ mentions satellite users will be able to see their colleagues from across the globe, no matter where they are.</span></span>

<span data-ttu-id="ee3f7-117">在聊天、頻道訊息及會議 IM 筆記/聊天的會議中，在小組體驗中的交談不是多地區感知，而且只會保留在租使用者的中央位置。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-117">Conversations in chats, channels messages, and meeting IM notes/chats within the Teams experience aren't Multi-Geo-aware and are all kept only inside the central location of the tenant.</span></span> <span data-ttu-id="ee3f7-118">通常，聊天交談不會套用至資料派駐需求。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-118">Typically, chat conversations aren’t applied to data residency needs.</span></span> <span data-ttu-id="ee3f7-119">如需詳細資訊，請參閱 [Microsoft 團隊中的資料位置](location-of-data-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-119">For more information, see [Location of data in Microsoft Teams](location-of-data-in-teams.md).</span></span>

<span data-ttu-id="ee3f7-120">如需多地理位置的詳細資訊，請參閱 [Microsoft 多地區功能頁面](https://aka.ms/multi-geo)。</span><span class="sxs-lookup"><span data-stu-id="ee3f7-120">For more info about Multi-Geo, refer to the [Microsoft Multi-Geo capabilities page](https://aka.ms/multi-geo).</span></span>
