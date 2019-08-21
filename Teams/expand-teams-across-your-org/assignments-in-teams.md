---
title: 團隊作業
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1keywords:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: 瞭解如何在 [教育版團隊中的 Microsoft 團隊系統管理中心] 中管理作業。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0eaaa4782ac1c0f5fa8d1618f89c05d3ffd58e57
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483976"
---
# <a name="assignments-in-teams-for-education"></a>在教育版小組中的作業

作業是指派給課程中的學生或團隊成員的工作或工作單位, 成為其研究的一部分。 您可以在團隊類別中建立作業。

[深入瞭解作業](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)

## <a name="assignments-in-the-microsoft-teams-admin-center"></a>Microsoft 團隊系統管理中心中的作業

使用 Microsoft 團隊系統管理中心的 [管理員設定], 您可以開啟或關閉下列功能, 以供貴組織內的學生和教師使用。 以下是與作業相關的設定:

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>每週監護人電子郵件摘要
[!INCLUDE [preview-feature](../includes/preview-feature.md)]

監護人電子郵件是傳送給學生的家長或監護人的每週電子郵件。 該電子郵件將會包含上周的工作分派及未來一周的作業相關資訊, 並將于週末傳送。 系統必須由管理員使用學校資料同步處理功能來更新電子郵件。

此設定預設為關閉。

<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
MakeCode 是一種區塊式編碼平臺, 可讓所有學生在生活中都能使用電腦科學。 

這個協力廠商產品或服務受限於自己的條款與隱私權原則。 您負責使用任何協力廠商產品和服務。

此設定預設為關閉。

[深入瞭解 MakeCode](https://www.microsoft.com/makecode)

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin
[!INCLUDE [preview-feature](../includes/preview-feature.md)]

Turnitin 是 plagiarism 偵測服務。 這個協力廠商產品或服務受限於自己的條款與隱私權原則。 您負責使用任何協力廠商產品和服務。

此設定預設為關閉。

若要為您的組織成功啟用 Turnitin, 您必須已經擁有 Turnitin 訂閱。 您必須輸入下列其他資訊, 這些資訊可在您的 Turnitin 系統管理主控台中找到:

  * _TurnitinApiKey_: 這是在系統管理主控台中的 [整合] 下找到的32字元 GUID。
  * _TurnitinApiUrl_: 這是您 Turnitin 系統管理主控台的 HTTPS URL。

以下是協助您取得此資訊的一些指示。

TurnitinApiUrl 是系統管理員主控台的主機位址。
範例. `https://your-tenant-name.turnitin.com`

系統管理主控台是您可以在其中建立整合與整合相關聯的 API 金鑰。

從**** 側邊功能表選取 [整合], 然後選取 [**新增整合**] 並提供名稱的整合。
![顯示新增整合的螢幕擷取畫面](./educationImages/Assignments_mopo_turnitin2.png)

在您遵循提示之後, 系統會為您提供 TurnitinApiKey。 複製 API 金鑰並貼到 Microsoft 團隊系統管理中心。  這只是您可以查看金鑰的唯一時機。
![螢幕擷取畫面顯示覆制 API 金鑰](./educationImages/Assignments_mopo_turnitin3.png)

按一下系統管理中心的 [**儲存**] 按鈕, 以取得此設定, 請允許長達24小時, 這些設定才會生效。

[深入瞭解 Turnitin 與 Microsoft 團隊之間的整合](https://www.turnitin.com/products/feedback-studio/microsoft-teams-integration)

[深入瞭解 Turnitin](https://www.turnitin.com/)
