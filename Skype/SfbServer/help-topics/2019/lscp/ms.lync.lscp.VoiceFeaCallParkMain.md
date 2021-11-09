---
title: 通話駐留
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaCallParkMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: b752617d-554d-470e-b17b-387403ac74ed
ROBOTS: NOINDEX, NOFOLLOW
description: 當來電停用時，會將通話轉移至暫留的臨時號碼，直到有人將通話轉移或下班時為止。您必須使用保留用於寄存通話的分機號碼範圍來設定表格。 這些分機號碼必須是虛擬分機 (亦即，未指派使用者或電話的分機) 。 每個執行通話駐留應用程式的集區，都可以有一個或多個範圍的分機。 在您的部署中，這些範圍必須是全域唯一的。
ms.openlocfilehash: f37913066bb2bf0a0eb6eec767501a3b16534ec6
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845696"
---
# <a name="call-park"></a>通話駐留

當來電停用時，會將通話轉移至暫留的臨時號碼，直到有人將通話轉移或下班時為止。您必須使用保留用於寄存通話的分機號碼範圍來設定表格。 這些分機號碼必須是虛擬分機 (亦即，未指派使用者或電話的分機) 。 每個執行通話駐留應用程式的集區，都可以有一個或多個範圍的分機。 在您的部署中，這些範圍必須是全域唯一的。

「 **通話駐留** 」頁面會顯示針對您組織所定義之所有通話駐留號碼範圍的清單。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以從「 **通話駐留** 」頁面執行下列工作：

- 建立新的號碼範圍

- 變更現有號碼範圍

- 刪除號碼範圍

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的命令。

- **新** 啟動新的通話駐留號碼範圍。

- **編輯** 開啟選取的號碼範圍進行編輯、選取清單中的所有號碼範圍，或刪除選取的號碼範圍。

- **Refresh** 重新整理號碼範圍清單。

下列清單說明頁面上的欄位。

- **名稱** 識別號碼範圍的唯一名稱。

- **起始範圍** 範圍的開始號碼。

- **結束範圍** 範圍的結束號碼。

- **目的地** 主機號碼範圍內主控通話駐留應用程式之應用程式服務的完整功能變數名稱 (FQDN) 或服務識別碼。

如需通話駐留功能及功能的詳細資訊，請參閱[Plan for 通話駐留 in 商務用 Skype](../../../plan-your-deployment/enterprise-voice-solution/call-park.md)。 如需與通話駐留號碼範圍搭配使用的詳細資訊，請參閱[Configure 電話號碼分機的停車電話](/previous-versions/office/lync-server-2013/lync-server-2013-configure-phone-number-extensions-for-parking-calls)。