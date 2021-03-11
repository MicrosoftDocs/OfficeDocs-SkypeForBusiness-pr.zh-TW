---
title: 未指派電話號碼建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
description: 未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派的號碼表可識別您希望用來處理撥打至未指派號碼的方式。
ms.openlocfilehash: 51c3f640bd9d98bcda9d5dd69406461e9c8393fd
ms.sourcegitcommit: c477aa1a7da0b6b9bea1f5d10f1395eef418bfdb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/10/2021
ms.locfileid: "50711740"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>未指派電話號碼：建立新的或編輯現有

未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。


> [!IMPORTANT]
> 當您結束建立新的未指派號碼範圍或編輯現有的未指派號碼範圍時，請按一下 [確定] 返回列出所有號碼範圍的「未指派號碼」頁面。除非您按一下「未指派號碼」頁面上的 [全部認可]，否則資料庫不會認可您在「新增未指派號碼範圍」頁面或「編輯未指派號碼範圍」頁面上所做的變更。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的欄位。

- **名稱** 請輸入識別未指派號碼範圍的描述性名稱。 在您儲存範圍之後，就無法變更此名稱。

- **號碼範圍** 在第一個欄位中，輸入未指派號碼範圍的開始號碼。 在第二個欄位中，輸入該範圍的結束號碼。

  - 該範圍的起始號碼必須小於或等於範圍的結束號碼。

  - 如果範圍的開始號碼或範圍的結束號碼包含分機號碼，則範圍的開始號碼和結束號碼都必須包含分機，且開始號碼和結束號碼的分機號碼必須相同。

  - 此數位必須符合正則運算式 `(tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?` 。 這表示 `tel:` 如果您未指定該字串將會自動為您新增) 、加號 (+) 及數位1到9，則 (的數位可以以字串開頭。 電話號碼最多可達 17 位，且後面可以再加分機，格式為 ;ext= 分機號碼。

- **宣告服務** 選取 [ **宣告** ]，讓宣告應用程式處理來電或 **exchange Um** ，讓 exchange um 自動語音應答處理傳入的呼叫。

- 若您選取 [宣告服務] 的 [宣告]：

  - **目的地伺服器的 FQDN** 選取執行宣告應用程式的應用程式服務的服務 ID，該應用程式會處理對此未指派號碼範圍的撥入呼叫。

  - **宣告** 選取要為此未指派號碼範圍播放的宣告。

- 若您選取 [宣告服務] 的 [Exchange UM]：

  - **自動語音應答電話號碼** 選取 Exchange UM 自動語音應答的電話號碼。

如需公告功能及功能的詳細資訊，請參閱規劃檔中的在 [商務用 Skype 2015 中規劃宣告應用程式](../../plan-your-deployment/enterprise-voice-solution/announcement.md) 。 如需使用未指派號碼範圍的詳細資訊，請參閱作業文件中的＜[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)＞。


