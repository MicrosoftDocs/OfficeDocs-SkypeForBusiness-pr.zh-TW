---
title: 未指定的電話號碼建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派號碼表指出您希望如何處理撥打至未指定號碼的通話。
ms.openlocfilehash: 87d83f6285e36abf6b063ba7d6c4d1a93cadc633
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41792161"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>未指派的電話號碼：建立新的或編輯現有號碼

> [!NOTE]
> 當您將商務用 Skype 2019 與 Exchange 2013 或 Exchange 2016 整合時，Exchange UM 仍可在商務用 Skype Server 2019 中使用。 由於 Exchange 2019 中的支援變更，因此需要取消 Exchange UM 整合，以取代雲端語音信箱和雲端自動語音應答功能。

未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派號碼表指出您希望如何處理撥打至未指定號碼的通話。

> [!IMPORTANT]
> 當您完成建立新的未指派編號範圍或編輯現有的數位範圍時，請按一下 **[確定]** ，返回列出所有數位範圍的 [**未指定的號碼**] 頁面。 您在新的 [**未指定**的數位範圍] 頁面或 [**編輯未指派的號碼] Rage**頁面上所做的變更，直到您在 [**未指定的號碼**] 頁面上按一下 [**全部提交**] 為止。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的欄位。

- **名稱**輸入識別未指定的數位範圍的描述性名稱。 在您儲存範圍之後，此名稱就無法變更。

- **數位範圍**在第一個欄位中，輸入未指定的數位範圍的起始編號。 在第二個欄位中，輸入範圍的結束數位。

  - 該範圍的起始號碼必須小於或等於範圍的結束號碼。

  - 如果範圍的起始編號或範圍的結束數位包含分機號碼，則起始編號與範圍的結束數位都必須包含延伸，且起始編號和所需的延伸號碼必須是相同的。結束數位。

  - 這個數位必須符合正則運算式（電話：）嗎？（\+)?[1-9] \d{0,17}（; ext = [1-9] \d{0,9}）？。 這表示數位可能會從電話號碼開始：（如果您沒有指定該字串將會自動新增為您），請使用加號（+），以及1到9的數位。 電話號碼最多可達 17 位，且後面可以再加分機，格式為 ;ext= 分機號碼。

- **宣告服務**選取 [**宣告**]，讓宣告應用程式處理撥出通話或**exchange Um** ，讓 exchange um 自動語音應答處理撥入通話。

- 如果您已選取 [**宣告**發佈**服務**]：

  - **目的地伺服器的 FQDN**選取執行宣告應用程式的應用程式服務的服務識別碼，該 app 服務會處理撥入通話至此範圍的未指定號碼。

  - **宣告**選取要在此未指定編號範圍中播放的宣告。

- 如果您已選取 [ **EXCHANGE UM**以供**宣告服務**]：

  - **自動助理電話號碼**選取 Exchange UM 自動語音應答的電話號碼。

如需公告功能和功能的詳細資訊，請參閱規劃檔中的[商務用 Skype 中的宣告應用程式規劃](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)。 如需使用未指派號碼範圍的詳細資訊，請參閱作業文件中的〈[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)〉。


