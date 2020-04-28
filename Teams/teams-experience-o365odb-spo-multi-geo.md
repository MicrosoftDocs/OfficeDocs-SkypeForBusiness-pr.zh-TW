---
title: Microsoft 365 或 Office 365 OneDrive 與 SharePoint Online 多地域租賃中的團隊體驗
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
audience: admin
description: 在本文中，您將學習如何在 Microsoft 365 或 Office 365 OneDrive 與 SharePoint Online 多地域租賃中使用團隊。
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
ms.openlocfilehash: 4e754177de6f08476c9160254f2334f6f3ac18d3
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/27/2020
ms.locfileid: "43903138"
---
<a name="teams-experience-in-a-microsoft-365-or-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Microsoft 365 或 Office 365 OneDrive 與 SharePoint Online 多地域租賃中的團隊體驗
===========================================

Microsoft 團隊是群組聊天軟體，也就是在 Office 365 中進行團隊合作的中心。 它是由 Microsoft 365 群組服務以及 SharePoint Online 和商務用 OneDrive 提供給其檔案體驗所支援。 在商務用 OneDrive/SharePoint Online 多地理租賃中，將租使用者延伸到許多地理位置（例如北美、歐洲和澳大利亞），基礎檔案體驗是多地區感知，所以小組使用檔案共同作業也是多地區的感知功能。 這是團隊在其原生檔案體驗中跨多個 Geos 託管之程式的主要前沿功能。

例如，在 Contoso 租賃中，將歐洲作為衛星地理位置，而北美作為地理位置，但在左窗格中的 [檔案] 索引標籤下，歐元的附屬使用者將會看到他或她的 OneDrive 檔案，不過這些檔案是託管在歐洲資料位置，而美國是租使用者的中心位置。 此外，使用者也可以在最近的 [查看] 薄片下存取最近使用過的檔案。 [最近的檔案] 可能包含使用者與其他 Geos 中的使用者共用的檔案，而且可能是受租使用者延伸的其他地理位置。 

指定團隊的群組網站也是多地區感知功能。 也就是說，如果歐洲的附屬使用者正在建立小組，則會在歐洲位置建立對應的群組網站，而與該小組群組相關聯的檔案將會保留在該位置。 任何後續的體驗（例如上傳新檔案或編輯檔案）都將針對該歐洲位置，以保證資料在這些檔案中保持常駐。 如此一來，基本的基礎 Microsoft 365 群組就能成為多地區感知，這一切都有可能完成。

因為多地域租賃是單一全域租使用者，所以在 @ 提及中，衛星使用者將能夠在全球各地查看其同事，無論其位於何處。 

請注意，小組體驗中的聊天與會議 IM 筆記中的交談並不是多地區感知，而且都只會保留在租使用者的中央位置。 通常，聊天交談不會套用至資料派駐需求。

如需 Office 365 多地理位置的詳細資訊，請參閱[Microsoft 多地區功能頁面](https://aka.ms/multi-geo)。