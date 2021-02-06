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
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>在 Microsoft 365 多地域租賃中的團隊體驗

Microsoft 團隊是群組聊天軟體，即在 Microsoft 365 和 Office 365 中進行團隊合作的中心。 它是由 Microsoft 365 群組服務以及 SharePoint Online 和商務用 OneDrive 提供給其檔案體驗所支援。 在商務用 OneDrive/SharePoint Online 多地理租賃中，將租使用者延伸至多個地理位置（例如北美、歐洲和澳大利亞），基礎檔案體驗是多地區感知，所以小組使用檔案共同作業也是多地區感知。 此功能是小組的主要主要功能，可供團隊在其原生檔案體驗中跨多個 Geos 託管的檔案。 這也包括 OneNote 和 Wiki 檔案。

例如，在 Contoso 租賃中，將歐洲作為衛星地理位置，而北美是中央地理位置，但在左窗格中的 [檔案] 索引標籤底下， **歐洲的使用者** 將會看到他們的 OneDrive 檔案，但檔案是託管在歐洲資料位置，而美國是租使用者的中央位置。 此外，使用者也可以在 **最近** 的 [查看] 薄片下存取最近使用過的檔案。 [最近的檔案] 可能包含從其他地域位置中的使用者共用的檔案。 

指定團隊的 SharePoint 網站也是多地區感知。 也就是說，如果歐洲的附屬使用者正在建立小組，則會在歐洲位置建立對應的 SharePoint 網站。 與該小組相關聯的檔案會保留在該位置的其他檔案中。 任何後續的體驗（例如上傳新檔案或編輯檔案）都將儲存在該歐洲位置，以保證資料在這些檔案中保持常駐。

因為多地域租賃是單一全域租使用者，所以在 @ 提及中，衛星使用者將能夠在全球各地查看其同事，不論他們身在何處。

在聊天、頻道訊息及會議 IM 筆記/聊天的會議中，在小組體驗中的交談不是多地區感知，而且只會保留在租使用者的中央位置。 通常，聊天交談不會套用至資料派駐需求。 如需詳細資訊，請參閱 [Microsoft 團隊中的資料位置](location-of-data-in-teams.md)。

如需多地理位置的詳細資訊，請參閱 [Microsoft 多地區功能頁面](https://aka.ms/multi-geo)。
