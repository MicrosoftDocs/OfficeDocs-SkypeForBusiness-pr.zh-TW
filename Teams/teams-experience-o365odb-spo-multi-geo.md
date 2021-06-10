---
title: Teams啟用多Microsoft 365環境中的體驗
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
description: 在本文中，您將瞭解如何在啟用多重地理位置Teams環境中Microsoft 365使用應用程式。
ms.openlocfilehash: a1b86cf83a0eabde81331e5311561aa1600d3c7e
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760536"
---
# <a name="teams-experience-in-a-microsoft-365-multi-geo-enabled-tenancy"></a>Teams多地理位置Microsoft 365租使用者體驗

Microsoft Teams是群組聊天軟體，是團隊合作和Microsoft 365 Office 365。 它由 Microsoft 365 群組服務以及 SharePoint Online 和 商務用 OneDrive提供其檔案體驗。 在 商務用 OneDrive/SharePoint Online 多地理位置 租使用者延伸到北美、歐洲和澳洲等多個地理位置的租使用者租使用者中，基礎檔案體驗是多重地理位置感知，因此Teams 檔案共同處理體驗也是多地理位置感知。 此功能是一項重要的前導功能，Teams原生檔案體驗中，跨多個地理位置託管的 Surface 檔案。 這也包括OneNote和 Wiki 檔案。

例如，在以歐洲為衛星地理和北美作為中央地理位置的 Contoso 租使用者中，歐洲衛星使用者將看到其 OneDrive 檔案在左窗格中的檔案卷號下，雖然檔案是位於歐洲資料位置，而美國是租使用者的中央位置。 此外，使用者可以在最近的視圖邊欄選項卡下存取 **最近使用的** 檔案。 最近的檔案可能包含來自其他地理位置使用者共用的檔案。 

一個小組的SharePoint網站也是多地理位置感知。 也就是說，如果歐洲衛星使用者正在建立團隊，則SharePoint將在歐洲位置建立對應的網站。 與該小組相關聯的檔案會保留在該位置。 任何後續的體驗 ，例如上傳新檔案或編輯檔案，都會儲存在該歐洲位置，並保留這些檔案的資料駐留承諾。

由於多重地理位置租使用者是單一全域租使用者，因此在 @ 提及期間，無論他們位於何處，衛星使用者都能看到來自全球各地的同事。

Teams 體驗中的聊天、頻道訊息和會議 IM 記事/聊天中的交談並非多重地理位置感知，而且只會保留在租使用者的中央位置內。 一般來說，聊天交談不會用於資料居住需求。 詳細資訊，請參閱資料在 Microsoft Teams[中的位置](location-of-data-in-teams.md)。

系統藍圖中Teams多地理位置Microsoft 365[支援](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=70783)。

有關 Multi-Geo 的資訊，請參閱 [Microsoft Multi-Geo 功能頁面](https://aka.ms/multi-geo)。
