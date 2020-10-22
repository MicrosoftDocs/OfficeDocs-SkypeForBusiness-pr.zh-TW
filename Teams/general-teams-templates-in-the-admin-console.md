---
title: 在系統管理中心使用一般團隊範本
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
description: 瞭解如何使用一般團隊範本，透過使用系統管理中心提供預先定義的設定、頻道及預先安裝的 app 來建立小組結構。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: a158850a70a0410c9be7cb434d6f0868d68218f5
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655500"
---
# <a name="use-general-teams-templates-in-the-admin-center"></a>在系統管理中心使用一般團隊範本

[!INCLUDE [preview-feature](includes/preview-feature.md)]

團隊範本可讓您透過提供預先定義的設定、通道及預先安裝應用程式範本，快速且輕鬆地建立團隊。

團隊範本有預先建立的小組結構定義，專為圍繞財務需求而設計。 您也可以延伸團隊範本，建立專為您特定組織需求量身定制的小組。

在本文中，我們將介紹每個團隊範本，並建議如何使用它們。

如果您負責規劃、部署及管理整個財務組織中的多個小組，本文將適合您。 您已在組織中部署團隊服務。 如果您還沒有推出小組，請先閱讀 [如何推出 Microsoft 團隊](How-to-roll-out-teams.md)。

若要深入瞭解小組範本的整體資訊，請參閱 [開始使用團隊範本](get-started-with-teams-templates-in-the-admin-console.md)。

## <a name="global-crisis-or-event"></a>全球危機或活動

針對您的危機小組集中共同作業，協助建立業務連續性方案、共用遠端工作秘訣、追蹤客戶通訊，以及使用宣告和新聞讓每個人都保持在迴圈中。

| 基底範本類型 |baseTemplateId| 此基礎範本隨附的屬性 |
| ------------------ |--|----------------------------------------------------------|
| 在全球危機或活動上共同作業 |`com.microsoft.teams.template.CollaborateOnAGlobalCrisisOrEvent` |管道 <ul><li>一般<li>公告</li><li>世界新聞</li><li>業務連續性</li><li>遠端作業</li><li>內部 comms</li><li>外部 comms</li><li>客戶投訴</li><li>Kudos</li><li>主管更新</li></ul>應用 <ul><li>稱讚</li><li>Wiki</li><li>Web</li></ul>|
||||

## <a name="adopt-office-365"></a>採納 Office 365

透過宣揚及協助對等新技術，協助您建立、擴大及維持您的擁護者社區推出。

| 基底範本類型 |baseTemplateId| 此基礎範本隨附的屬性 |
| ------------------|--|-----------------------------------------------------------|
| 採納 Office 365 | `com.microsoft.teams.template.AdoptOffice365` |  管道 <ul><li>一般</li> <li>公告</li> <li>擁護方角落</li> <li>小組表單</li></ul> 應用 <ul><li>Wiki</li>  <li>行事曆</li><li>技能開發</li><li>貸款處理</li><li>客戶投訴</li><li>Kudos</li><li>有趣的內容</li><li>合規性</li></ul>|
||||

## <a name="manage-a-project"></a>管理專案

使用此範本管理一般專案管理的工作、共用文件、執行專案會議及記錄風險與決策。

| 基底範本類型| baseTemplateId| 此基礎範本隨附的屬性 |
| ------------------|--|-----------------------------------------------------------|
| 管理專案| ManageAProject 中的 [.com] 範本  | 管道 <ul><li>一般</li> <li>公告</li> <li>資源清單</li> <li>規劃</li></ul> 應用<ul><li>Wiki</li><li>OneNote</li></ul> |
||||

## <a name="manage-an-event"></a>管理活動

管理工作、檔，以及共同作業，以提供引人注目的活動所需的所有專案。 邀請來賓使用者在貴公司內部和外部都能安全地共同作業。

您可能無法以應用程式許可權原則存取某些應用程式。

| 基底範本類型 | baseTemplateId| 此基礎範本隨附的屬性 |
| ------------------ |--|-----------------------------------------------------------|
| 管理活動| `com.microsoft.teams.template.ManageAnEvent` | 管道 <ul><li>一般</li> <li>公告</li> <li>預算</li> <li>內容</li><li>物流</li> <li>規劃</li> <li> 行銷與 PR</li></ul> 應用<ul><li>Wiki</li><li>Web</li> <li>YouTube</li> <li>Planner</li> <li>OneNote</li></ul> |
||||

## <a name="onboard-employees"></a>板載員工

利用此中心小組的資源、問題及有趣的樂趣，改善您的文化，並簡化您的員工加入。

| 基底範本類型 |baseTemplateId| 此基礎範本隨附的屬性 |
| ------------------|--|-----------------------------------------------------------|
|板載員工|`com.microsoft.teams.template.OnboardEmployees`  | 管道 <ul><li>一般</li> <li>公告</li> <li>員工聊天</li> <li>訓練</li></ul>應用<ul><li>Wiki</li><li>社區</li></ul>|
||||

## <a name="organize-a-help-desk"></a>組織技術支援中心

在支援您的支援人員的檔、原則及流程上共同作業。 整合現有的票證發放系統，或使用我們的範本來管理要求。

| 基底範本類型 |baseTemplateId| 此基礎範本隨附的屬性 |
| ------------------|--|------------------------------------------------------------|
|組織技術支援中心|`com.microsoft.teams.template.OrganizeHelpDesk`| 管道<ul><li>一般</li><li>公告</li><li>常見問題集</li></ul>應用<ul><li>Wiki</li><li>OneNote</li></ul> |
||||
