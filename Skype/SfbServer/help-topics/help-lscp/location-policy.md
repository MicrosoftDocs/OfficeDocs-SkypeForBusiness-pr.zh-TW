---
title: 位置原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.NcsLocMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5530cf17-4520-40b5-ba70-c62692685048
description: 位置原則決定是否啟用增強型 9-1-1 (E9-1-1) 及其使用方式，以及針對使用者和連絡人使用位置資訊的方式。
ms.openlocfilehash: e780256ba025328c6a84d709aaa4c6f522b219df
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700098"
---
# <a name="location-policy"></a>位置原則

位置原則決定是否啟用增強型 9-1-1 (E9-1-1) 及其使用方式，以及針對使用者和連絡人使用位置資訊的方式。

位置原則包含全域原則，也可能會包含一或多項網站與使用者原則：

- **全域原則：** 預設會建立全域原則。 您可以編輯全域原則，但無法將其刪除。 如果您嘗試移除全域原則，所有設定都將重設為預設值。

- **網站原則（選用）：** 您可以建立一或多個網站位置原則，每個都適用于特定網站。 網站原則會覆寫全域原則。

- **使用者原則（選用）：** 您可以建立一或多個使用者位置原則，每個都適用于特定的使用者或使用者群組。 使用者原則會覆寫全域原則和網站原則。

> [!NOTE]
> 您也可以指派位置原則給網站 (即子網路群組)。 指派給網站的位置原則，優先於其他所有使用者原則。 如需使用 Cmdlet 將位置原則指派給網路網站的詳細資料，請參閱[在商務用 Skype Server 2015 中新增位置原則至網路網站](../../deploy/deploy-enterprise-voice/add-a-location-policy-to-a-network-site.md)。 如需使用商務用 Skype Server [控制台] 將位置原則指派給網路網站的詳細資料，請參閱設定[網路網站](https://technet.microsoft.com/library/358aa08a-c5bc-45fc-8017-19e6202f88c5.aspx)。

「位置原則」**** 頁面會顯示為您組織所定義之所有位置原則的清單。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以從「位置原則」**** 頁面執行下列工作：

- 建立新的網站位置原則或使用者位置原則

- 變更全域原則或現有的網站原則或使用者原則

- 刪除網站原則或使用者原則

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的命令。

- **新增**啟動新的網站位置原則或使用者位置原則。

- [**編輯**]開啟所選的位置原則以進行編輯、選取清單中的所有位置原則，或刪除選取的網站原則或使用者原則。

    > [!NOTE]
    > **刪除**   會將全域原則的設定重設為預設值。

- **更新**刷新位置原則的清單。

下列清單說明頁面上的欄位。

- **名稱**識別位置原則。

- **範圍**識別位置原則的範圍： [全域]、[網站] 或 [使用者]。

- **E9-1-1**已檢查是否已針對 E9-1-1 啟用指派此位置原則的使用者。

- **位置**指定使用者在新位置使用商務用 Skype Server 登錄時，是否提示使用者輸入位置資訊，以及他們是否在沒有輸入位置資訊的情況下關閉提示時，才會看到免責聲明。

- **PSTN 使用量**指定公用的交換電話網絡（PSTN）用法，用來判斷用來從使用這個設定檔的用戶端路由緊急呼叫的語音路線。

- **E9-1-1 個數字**指定要撥打緊急服務的電話號碼。

- **E9-1-1 蒙板**指定使用者撥號的號碼，然後將它轉換成緊急電話撥號碼。

如需企業語音緊急服務功能和功能的詳細資訊，請參閱規劃檔中的[E9-1-](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 1。 如需使用位置原則的詳細資訊，請參閱作業文件中的〈[Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)〉。


