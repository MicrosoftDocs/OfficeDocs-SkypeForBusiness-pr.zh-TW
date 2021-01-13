---
title: 未指派電話號碼
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
description: 未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派的號碼表可識別您希望用來處理撥打至未指派號碼的方式。
ms.openlocfilehash: 4b736aef028421bca6c4945095f9d293d18f3550
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826883"
---
# <a name="unassigned-phone-number"></a>未指派電話號碼

未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派的號碼表可識別您希望用來處理撥打至未指派號碼的方式。

設定未指派號碼表的方式取決於其使用方式。您可以設定包含組織所有有效分機號碼、只包含未指派的分機號碼，或包含結合這兩種類型之號碼的表格。未指派號碼表可以同時包含已指派和未指派的號碼，但是只有在來電者撥打目前未指派的號碼時才會叫用。如果您在未指派號碼表中納入所有有效的分機號碼，可以指定每次某人離開組織時要執行的動作，而不必重新設定表格。如果表格中包含未指派的分機號碼，您可以針對特定號碼設計要採取的動作。例如，如果您變更客戶服務人員的分機號碼，則可以在表格中包含舊的客戶服務號碼，並且將它指派給提供新號碼的宣告。

> [!IMPORTANT]
> 您必須先定義一個或多個宣告或設定 Exchange UM 自動語音應答，才能設定未指派號碼表。

「未指派的號碼」頁面會顯示為組織定義的未指派號碼範圍清單。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「未指派的號碼」頁面上執行下列工作：

- 建立新的未指派號碼範圍

- 變更現有的未指派號碼範圍

- 刪除未指派的號碼範圍

- 變更未指派的號碼範圍順序，以決定哪個動作要先套用至符合未指派號碼的來電。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的命令。

- **新** 啟動新的未指派號碼範圍。

- **編輯** 開啟所選取的未指派號碼範圍進行編輯、選取清單中所有未指派的號碼範圍，或刪除選取的未指派號碼範圍。

- **上移** 將選取的未指派號碼範圍上移到清單中，以便商務用 Skype 伺服器會儘早找到它，並套用指定的動作，再對清單中的其他範圍套用指定的動作。

    > [!NOTE]
    > 商務用 Skype Server 會從上到下搜尋未指派號碼表格，並使用符合未指派號碼的第一個範圍。 例如，如果您有一個範圍指定的是最後不得不採取的動作，請確定該範圍位於清單底部。

- **下移** 在清單中將所選取的未指派號碼範圍下移。

- **全部認可** 儲存您對未指派號碼範圍所做的所有變更。

    > [!IMPORTANT]
    > 此命令會儲存您在「新增未指派的號碼」頁面和「編輯未指派的號碼」頁面上進行的所有變更。

- **Refresh** 重新整理未指派號碼範圍的清單。

下列清單說明頁面上的欄位。

- **名稱** 識別未指派號碼範圍的唯一名稱。

- **狀態** 顯示哪些號碼範圍已儲存至資料庫，哪些尚未儲存。

- **起始範圍** 未指派號碼範圍的開始號碼。

- **結束範圍** 未指派號碼範圍的結束號碼。

- **目的地** 主控宣告應用程式之應用程式服務的服務 ID，會處理對此未指派號碼範圍的撥入呼叫。

- **宣告** 將為此未指派號碼範圍播放的宣告。

如需公告功能及功能的詳細資訊，請參閱規劃檔中的在 [商務用 Skype 2015 中規劃宣告應用程式](../../plan-your-deployment/enterprise-voice-solution/announcement.md) 。 如需使用未指派號碼範圍的詳細資訊，請參閱作業文件中的＜[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)＞。


