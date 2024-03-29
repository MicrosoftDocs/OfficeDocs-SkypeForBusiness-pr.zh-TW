---
title: 位置原則
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: 位置原則決定是否要啟用增強型 9-1-1 (E9-1-1)、其使用方式，以及位置資訊對於使用者與連絡人的運用方式。
ms.openlocfilehash: a7173a4b7598d3645aeb9ddd02f7dcbaad88f585
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393995"
---
# <a name="location-policy"></a>位置原則

位置原則決定是否要啟用增強型 9-1-1 (E9-1-1)、其使用方式，以及位置資訊對於使用者與連絡人的運用方式。

位置原則包含全域原則，也可能會包含一或多項網站與使用者原則：

- **全域原則：** 預設會建立全域原則。 您可以編輯全域原則，但無法加以刪除。 如果您嘗試移除全域原則，則所有設定都會重設為預設值。

- **網站原則 (選用) ：** 您可以建立一或多個網站位置原則，每個網站位置原則都適用于特定網站。 網站原則會覆寫全域原則。

- **使用者原則 (選用) ：** 您可以建立一或多個使用者位置原則，每個使用者位置原則都適用于特定的使用者或使用者群組。 使用者原則會覆寫全域原則及網站原則。

> [!NOTE]
> 您也可以指派位置原則給網站 (即子網路群組)。 指派給網站的位置原則，優先於其他所有使用者原則。 如需使用 Cmdlet 指派位置原則給網路網站的詳細資訊，請參閱[在商務用 Skype Server 2015 中新增位置原則至網站](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)。 如需使用商務用 Skype Server 控制台將位置原則指派至網站的詳細資訊，請參閱設定[網路網站](/previous-versions/office/lync-server-2013/lync-server-2013-creating-or-modifying-network-sites)。

「位置原則」頁面會顯示為您組織所定義之所有位置原則的清單。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可從「位置原則」頁面執行下列工作：

- 建立新的網站位置原則或使用者位置原則

- 變更全域原則或現有的網站原則或使用者原則

- 刪除網站原則或使用者原則

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的命令。

- **新增功能** 啟動新的網站位置原則或使用者位置原則。

- **編輯** 開啟選取的位置原則以進行編輯、選取清單中的所有位置原則，或刪除選取的網站原則或使用者原則。

    > [!NOTE]
    > **刪除** 會將全域原則的設定重設為預設值。

- **刷新** 重新整理位置原則清單。

下列清單說明頁面上的欄位。

- **名字** 識別位置原則。

- **範圍** 識別位置原則的範圍：全域、網站或使用者。

- **E9-1-1** 已檢查是否已對 E9-1-1 啟用指派此位置原則的使用者。

- **位置** 指定使用者在其用戶端以新位置商務用 Skype Server 註冊時，是否要提示使用者輸入位置資訊，以及是否要在不輸入位置資訊的情況下，在取消提示時看到免責聲明。

- **PSTN 使用** 方式指定公用交換電話網路 (PSTN) 使用方式，用來判斷用來從使用此設定檔的用戶端路由緊急通話的語音路由。

- **E9-1-1 號碼** 指定要撥通緊急服務的號碼。

- **E9-1-1 遮罩** 指定使用者撥號的號碼，然後將其轉譯成緊急撥號號碼。

如需企業語音緊急服務功能及功能的詳細資訊，請參閱規劃檔中的[E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) 。 如需使用位置原則的詳細資訊，請參閱作業文件中的＜[Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information)＞。