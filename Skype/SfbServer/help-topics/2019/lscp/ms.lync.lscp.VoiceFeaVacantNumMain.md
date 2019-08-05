---
title: 未指派電話號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24eca749-a9f3-40e7-839b-d21c3ef7d533
ROBOTS: NOINDEX, NOFOLLOW
description: 未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派號碼表指出您希望如何處理撥打至未指定號碼的通話。
ms.openlocfilehash: 684519d29177b9daf4be57c650e811f00945adfb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191671"
---
# <a name="unassigned-phone-number"></a>未指派電話號碼

> [!NOTE]
> 當您將商務用 Skype 2019 與 Exchange 2013 或 Exchange 2016 整合時, Exchange UM 仍可在商務用 Skype Server 2019 中使用。 由於 Exchange 2019 中的支援變更, 因此需要取消 Exchange UM 整合, 以取代雲端語音信箱和雲端自動語音應答功能。

未指派號碼是對您的組織有效但未指派給使用者或電話的電話號碼。未指派號碼表指出您希望如何處理撥打至未指定號碼的通話。

設定未指派號碼表的方式取決於其使用方式。您可以設定包含組織所有有效分機號碼、只包含未指派的分機號碼，或包含結合這兩種類型之號碼的表格。未指派號碼表可以同時包含已指派和未指派的號碼，但是只有在來電者撥打目前未指派的號碼時才會叫用。如果您在未指派號碼表中納入所有有效的分機號碼，可以指定每次某人離開組織時要執行的動作，而不必重新設定表格。如果表格中包含未指派的分機號碼，您可以針對特定號碼設計要採取的動作。例如，如果您變更客服人員的分機號碼，則可以在表格中包含舊的客服號碼，並且將它指派給提供新號碼的宣告。

> [!IMPORTANT]
> 您必須先定義一個或多個宣告或設定 Exchange UM 自動語音應答，才能設定未指派號碼表。

「未指派的號碼」**** 頁面會顯示為組織定義的未指派號碼範圍清單。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「未指派的號碼」**** 頁面上執行下列工作：

- 建立新的未指派號碼範圍

- 變更現有的未指派號碼範圍

- 刪除未指派的號碼範圍

- 變更未指派的號碼範圍順序，以決定哪個動作要先套用至符合未指派號碼的來電。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的命令。

- **新增**開始新的未指派的數位範圍。

- [**編輯**]開啟選取的未指定的數位範圍進行編輯, 選取清單中所有未指定的數位範圍, 或刪除選取的未指定的數位範圍。

- **上移**在清單中將選取的未指派的數位範圍往上移動, 讓商務用 Skype 伺服器更快找到並套用指定的動作, 然後再針對清單中的其他範圍套用所指定的動作。

    > [!NOTE]
    > 商務用 Skype Server 會從上到下搜尋 [未指定的數位] 資料表, 並使用符合未指定數位的第一個範圍。 例如，如果您有一個範圍指定的是最後不得不採取的動作，請確定該範圍位於清單底部。

- **向下移動**在清單中將選取的未指派的數位範圍向下移動。

- **全部確認**儲存您對未指派的數位範圍所做的所有變更。

    > [!IMPORTANT]
    > 此命令會儲存您在「新增未指派的號碼」**** 頁面和「編輯未指派的號碼」**** 頁面上進行的所有變更。

- **更新**刷新未指派的數位範圍清單。

下列清單說明頁面上的欄位。

- **名稱**識別未指定的數位範圍的唯一名稱。

- **狀態**顯示已儲存至資料庫並沒有的數位範圍。

- **起始範圍**未指定的數位範圍的起始編號。

- **結束範圍**未指定的數位範圍的結束數位。

- **目的地**主持宣告應用程式的應用程式服務的服務識別碼, 會處理撥入呼叫到此未指定號碼的範圍。

- **宣告**將針對此未指定編號範圍播放的公告。

如需公告功能和功能的詳細資訊, 請參閱規劃檔中的[商務用 Skype 中的宣告應用程式規劃](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)。 如需使用未指派號碼範圍的詳細資訊，請參閱作業文件中的〈[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)〉。


