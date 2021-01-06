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
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>在 Microsoft 365 多地域租賃中的團隊體驗

Microsoft 團隊是群組聊天軟體，即在 Microsoft 365 中進行團隊合作的中心。 它由 Microsoft 365 群組服務提供支援，以及 SharePoint 和 OneDrive 的檔案體驗。 在已將租使用者延伸至多個地理位置（例如北美、歐洲和澳大利亞）的多地域組織中，基本的檔案體驗是多地區感知，所以小組使用檔案共同作業也能感知多地區。 這可讓團隊在其原生檔案體驗中跨多個地理位置託管的 surface 檔。

例如，在 Contoso 租賃中，將歐洲作為衛星地理位置，而北美作為地理位置，但在左窗格中的 [檔案] 索引標籤下，歐元的附屬使用者將會看到他或她的 OneDrive 檔案，不過這些檔案是託管在歐洲資料位置，而美國是租使用者的中心位置。 此外，使用者也可以在最近的 [查看] 薄片下存取最近使用過的檔案。 [最近的檔案] 可能包含從其他地域位置中的使用者共用的檔案。 

指定的小組的 SharePoint 網站也是多地區感知功能。 也就是說，如果歐洲的附屬使用者正在建立小組，則會在歐洲位置建立對應的 SharePoint 網站，並將與該小組相關聯的檔案保留在該位置。 任何後續的體驗（例如上傳新檔案或編輯檔案）都將儲存在該歐洲位置，以保證資料在這些檔案中保持常駐。

請注意，小組體驗中的聊天與會議 IM 筆記中的交談並不是多地區感知，而且都只會保留在組織的中央位置。

如需多地理位置的詳細資訊，請參閱 [Microsoft 多地區功能](https://aka.ms/multi-geo)。
