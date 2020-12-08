---
title: 團隊作業
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: jastark
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.assignments.overview
- ms.teamsadmincenter.assignments.tooltip.emaildigest
- ms.teamsadmincenter.assignments.tooltip.makecode
- ms.teamsadmincenter.assignments.tooltip.turnitin
description: 瞭解如何在 [教育版團隊中的 Microsoft 團隊系統管理中心] 中管理作業。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 64be355da30feb3c629569f583897353c21cfa37
ms.sourcegitcommit: 481d18b76304adfa340b5f1b2f1b7965e9ff4993
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/07/2020
ms.locfileid: "49586616"
---
# <a name="assignments-in-teams-for-education"></a>Teams 教育版中的作業

在教育版團隊中的 [作業及成績] 功能可讓教師指派工作、工作或測驗給學生。 教育者可以管理作業時間軸、指示、新增資源以供使用，以及量表的成績及其他功能。 他們也可以在 [成績] 索引標籤中追蹤班級與個別學生的進度。

[深入瞭解團隊中的作業與成績教育](https://support.office.com/article/microsoft-teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114?ui=en-US&rs=en-IE&ad=IE#ID0EAABAAA=Assignments)。

> [!Note]
> 如需不同平臺上團隊作業的詳細資料，請參閱 [依平臺的團隊功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。

## <a name="assignments-integrations-in-the-microsoft-teams-admin-center"></a>Microsoft 團隊系統管理中心的作業整合

使用 Microsoft [團隊管理中心] 的 [管理員設定]，您可以開啟或關閉貴組織內部或其學生的相關功能。 以下是與作業相關的設定：

<a name="#bkemaildigest"> </a>
### <a name="weekly-guardian-email-digest"></a>每週監護人電子郵件摘要


監護人電子郵件會在每個週末傳送給家長或監護人。 電子郵件包含上一周的作業相關資訊，以及即將到來的周。 您可以使用 [學校資料同步](https://docs.microsoft.com/schooldatasync/parent-contact-sync)處理來設定家長和監護人同步處理。

1. 透過父母和監護人同步處理 SDS 中的家長連絡人資訊。 如需如何啟用家長和監護人同步處理的指示，請參閱 [啟用家長和監護人同步](https://docs.microsoft.com/schooldatasync/parent-contact-sync#enabling-parent-and-guardian-sync)處理。

2. 在 Microsoft 團隊系統管理中心開啟監護人設定，因為預設會關閉設定。 這可讓教師傳送每週摘要。

   > [!NOTE]
   > 教師可以選擇不使用摘要，方法是在自己的個人班級小組中取消選擇該設定， ([ **作業設定] > 家長/監護人電子郵件**) 。

若要確認家長會收到電子郵件，必須成立下列三個專案：

 - 附加至 SDS 中的學生個人檔案並將其標記為 _家長_ 或 _監護人_ 的電子郵件地址。 如需詳細資訊，請參閱 [家長和監護人同步處理檔案格式](https://docs.microsoft.com/schooldatasync/parent-contact-sync-file-format)。

 - 學生至少屬於一個課程，該課程中的電子郵件未由教師在 [作業設定](https://support.microsoft.com/office/adjust-assignment-settings-in-your-class-team-05bb3b89-1cdf-415a-b6c7-44add0376a77)中停用。

 - 該電子郵件將會包含前一周或下周的到期日作業的相關資訊。

此功能的預設設定為 [ **關閉**]。


<a name="bkmakecode"> </a>
### <a name="makecode"></a>MakeCode
Microsoft MakeCode 是一種區塊式編碼平臺，可讓所有學生都能使用電腦科學。 

MakeCode 是一種受 Microsoft [使用條款](https://go.microsoft.com/fwlink/?LinkID=206977) 與 [隱私權](https://go.microsoft.com/fwlink/?LinkId=521839) 原則制約的 microsoft 產品。

此功能的預設設定為 [ **關閉**]。

若要在 [團隊] 中啟用 MakeCode 作業，請移至 [ **團隊系統管理中心**]，流覽至 [ **作業** ] 區段，然後將 [MakeCode 切換] 選項開啟為 [ **開啟**]。 按一下 [儲存]。 等待幾個小時，這些設定才會生效。

如需此功能的運作方式的詳細資訊，請參閱此 [視頻示範](https://makecode.com/blog/teams/teams-assignments)。

[深入瞭解 MakeCode](https://aka.ms/makecode)。

<a name="#turnitin"> </a>
### <a name="turnitin"></a>Turnitin

[Turnitin](https://www.turnitin.com/) 是一種學術的完整性服務。 這是協力廠商產品或服務，受限於它本身的條款與隱私權原則。 您負責使用任何協力廠商產品和服務。

此功能的預設設定為 [ **關閉**]。

若要為您的組織啟用 Turnitin，您將需要 Turnitin 訂閱。 接著，您可以輸入下列資訊，這些資訊可在您的 Turnitin 系統管理主控台中找到：

  * **TurnitinApiKey**：這是在系統管理主控台中的 [整合] 下找到的32字元 GUID。
  * **TurnitinApiUrl**：這是您 Turnitin 系統管理主控台的 HTTPS URL。

以下是協助您取得此資訊的一些指示。

**TurnitinApiUrl** 是系統管理員主控台的主機位址。
範例 `https://your-tenant-name.turnitin.com`

系統管理主控台是您可以在其中建立整合與整合相關聯的 API 金鑰。

從側邊功能表選取 [整合]， **然後選取 [** **新增整合** ] 並提供名稱的整合。

![顯示新增整合的螢幕擷取畫面](./educationImages/Assignments_mopo_turnitin2.png)

在您遵循提示之後，系統會為您提供 **TurnitinApiKey** 。 複製 API 金鑰並貼到 Microsoft 團隊系統管理中心。  這只是您可以查看金鑰的唯一時機。

![螢幕擷取畫面顯示覆制 API 金鑰](./educationImages/Assignments_mopo_turnitin3.png)

按一下系統管理中心的 [ **儲存** ] 按鈕時，設定才會生效數小時。

