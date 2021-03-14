---
title: 在系統管理中心中使用 Teams 零售業範本
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
description: 了解如何使用 Teams 範本，使用系統管理中心透過提供預先定義的設定、頻道和預先安裝的應用程式，以建立專為零售商需求設計的團隊結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b40da8fd1cc8182d0e5ad80c30f5a459f17d26f
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662638"
---
# <a name="use-teams-retail-templates-in-the-admin-center"></a>在系統管理中心中使用 Teams 零售業範本

Teams 範本提供預先定義的設定、頻道和預先安裝應用程式範本，讓您快速且輕鬆地建立團隊。

Teams 範本具有專為零售商需求設計的團隊結構預先建立的定義。 您可以使用 Teams 範本快速建立適合零售商的團隊類型，並在整個組織中部署。 您也可以擴充 Teams 範本，以建立專為您特定組織需求量身打造的團隊。

本文將介紹各個 Teams 範本，並建議如何使用範本。

如果您負責規劃、部署和管理整個零售組織的多個團隊，本文適合您。 我們假定您已在組織中部署 Teams 服務。 如果您尚未推出 Teams，請先閱讀[如何推出 Microsoft Teams](How-to-roll-out-teams.md)。

如需深入了解一般 Teams 範本，請參閱 [Teams 範本入門](get-started-with-teams-templates-in-the-admin-console.md)。

## <a name="organize-a-store"></a>組織商店

將零售員工彙集在集中的體驗，以管理工作、共用文件及解決客戶問題。 整合其他應用程式，以簡化班次的開始與結束程序。

| 基本範本類型 |baseTemplateId | 此基本範本提供的屬性 |
| ------------------|-- |----------------------------------------------------- |
|組織商店|`retailStore`|頻道： <ul><li>一般<li>班次交班</li><li>學習</li></ul> 應用程式： <ul><li>Wiki</li></ul>|
||||

## <a name="manager-collaboration"></a>主管共同作業

管理員共同作業範本適合用來建立團隊，以讓一組主管跨商店及區域等進行共同作業。例如，如果您的組織有不同地區，您可以為加州地區建立主管共同作業團隊，並包含該區域的所有商店主管，以及該地區的地區主管。

| 基本範本類型| baseTemplateId | 此基本範本提供的屬性 |
| ------------------|- |----------------------------------------------------- |
|零售 - 主管共同作業|`retailManagerCollaboration` |頻道： <ul><li>一般<li>營運</li><li>學習</li></ul> 應用程式： <ul><li>Wiki</li></ul>|
||||
