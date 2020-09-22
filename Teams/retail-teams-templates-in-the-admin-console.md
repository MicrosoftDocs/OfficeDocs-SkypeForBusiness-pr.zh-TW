---
title: 在管理員主控台中使用團隊零售範本
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用 [團隊範本]，透過使用管理主控台提供預先定義的設定、通道及預先安裝應用程式，來建立專為零售商需求而設計的小組結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 8b72fe7b1f101278d206d49f06203fe9841ba25f
ms.sourcegitcommit: af9f96010460f9323db84912fe143aa0750ac798
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171077"
---
# <a name="use-teams-retail-templates-in-the-admin-console"></a>在管理員主控台中使用團隊零售範本

[!INCLUDE [template](includes/preview-feature.md)]

團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本，快速且輕鬆地建立團隊。

團隊範本擁有圍繞零售商需求設計之小組結構的預先建立的定義。 您可以使用團隊範本快速建立適用于零售商的團隊類型，並在整個組織中進行部署。 您也可以延伸團隊範本，建立專為您特定組織需求量身定制的小組。

在本文中，我們將介紹每個團隊範本，以及我們建議使用這些範本的方式。

如果您負責規劃、部署及管理多個零售組織中的多個小組，本文適用于您。 我們假設您已在貴組織中已部署團隊服務。 如果您還沒有推出小組，請先閱讀 [如何推出 Microsoft 團隊](How-to-roll-out-teams.md)。

若要深入瞭解小組範本的整體資訊，請參閱 [開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。

## <a name="organize-a-store"></a>整理商店

將您的零售員工集中在一個集中體驗中，以管理工作、共用文件並解決客戶問題。 整合其他應用程式，以簡化倒班開始 & 結束程式。

| 基底範本類型 |baseTemplateId | 此基礎範本隨附的屬性 |
| ------------------|-- |----------------------------------------------------- |
|整理商店| `retailStore`|管道 <ul><li>一般<li>倒班切換</li><li>教學</li></ul> 應用 <ul><li>Wiki</li></ul>|
||||

## <a name="manager-collaboration"></a>Manager 共同作業

Manager 共同工作範本適用于為一組主管建立小組，以便在商店/地區等共同作業。例如，如果您的組織有地區，您可以為加利福尼亞地區建立經理共同作業小組，並包含該地區的所有書店管理員，以及該地區的地區經理。

| 基底範本類型| baseTemplateId | 此基礎範本隨附的屬性 |
| ------------------|- |----------------------------------------------------- |
|零售經理共同作業|`retailManagerCollaboration` |管道 <ul><li>一般<li>營運</li><li>教學</li></ul> 應用 <ul><li>Wiki</li></ul>|
||||
