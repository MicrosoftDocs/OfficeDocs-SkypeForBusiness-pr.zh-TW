---
title: 用戶端版本原則建立新的或編輯現有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: 您可以指定環境中支援的用戶端版本。 當執行不同版本的兩個用戶端互動時，這兩個用戶端可用的功能會受限於彼此的功能。 若要充分運用商務用 Skype Server 2015 隨附的功能, 並改善總體使用者體驗, 您可以使用用戶端版本篩選來限制在您的環境中使用的用戶端版本。 使用用戶端版本篩選器還可幫助您降低支援多個用戶端版本的相關成本。
ms.openlocfilehash: f89089f34086a36c3e652bf8527ba4db7d108a11
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36193172"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>用戶端版本原則：建立新的或編輯現有原則

您可以指定環境中支援的用戶端版本。 當執行不同版本的兩個用戶端互動時，這兩個用戶端可用的功能會受限於彼此的功能。 若要充分運用商務用 Skype Server 2015 隨附的功能, 並改善總體使用者體驗, 您可以使用用戶端版本篩選來限制在您的環境中使用的用戶端版本。 使用用戶端版本篩選器還可幫助您降低支援多個用戶端版本的相關成本。

> [!IMPORTANT]
> 篩選器會依優先順序列出。例如，如果您有一個可讓執行 1.5 版的用戶端連線的篩選器，後面接著一個封鎖執行 2.0 以前版本之用戶端的篩選器，則第一個篩選器的優先順序高於第二個，而且執行 1.5 版的用戶端可以連線。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「新增用戶端版本原則」**** 或「編輯用戶端版本原則」**** 頁面上執行下列工作：

- 新增或修改用戶端版本原則的名稱或描述。

- 新增或修改用戶端版本原則的用戶端版本規則。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。

- **範圍**識別用戶端版本原則的範圍 (網站、池或使用者)。

- **名稱**您可以新增或修改用戶端版本原則的名稱。

- **描述**您可以在 [用戶端版本原則] 頁面上的清單中新增描述, 以協助識別原則。

- **新增**您可以將新的用戶端版本規則新增至原則。

- **顯示詳細資料**這個選項會開啟一個對話方塊, 您可以在其中變更用戶端版本規則的選項。

- **移除**此選項會從原則中移除選取的用戶端版本規則。

- **向上鍵和向下鍵**此選項會將選取的用戶端版本規則在 [優先順序] 中向上或向下移動。 規則會按照所列的順序進行處理。

如需用戶端和用戶端版本間互通性的詳細資訊，請參閱規劃文件中的〈[Client Interoperability in Lync 2013 Preview](https://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)〉。如需使用用戶端版本原則的詳細資訊，請參閱作業文件中的〈[Specify the Client Versions Supported in Your Organization](https://technet.microsoft.com/library/d256a581-9a48-4d1a-82cc-2e1f520d7d2e.aspx)〉。

