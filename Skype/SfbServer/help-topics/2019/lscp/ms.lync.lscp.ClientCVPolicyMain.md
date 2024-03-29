---
title: 用戶端版本原則
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 4f84bc0f-e1df-4acb-b8ef-57f165b0153b
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以指定環境中支援的用戶端版本。 當執行不同版本的兩個用戶端互動時，這兩個用戶端可用的功能會受限於彼此的功能。
ms.openlocfilehash: 52282e98cbf7f504dcfdc26dd74f8e4e82cb711c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62391795"
---
# <a name="client-version-policy"></a>用戶端版本原則

您可以指定環境中支援的用戶端版本。 當執行不同版本的兩個用戶端互動時，這兩個用戶端可用的功能會受限於彼此的功能。 若要充分運用商務用 Skype Server 所包含的功能，以及改善整體使用者體驗，您可以使用用戶端版本篩選器來限制環境中所用的用戶端版本。 使用用戶端版本篩選器還可幫助您降低支援多個用戶端版本的相關成本。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「用戶端版本原則」頁面上執行下列工作：

- 編輯預設 ( **全域**) 用戶端版本原則。

- 為特定網站或集區建立用戶端版本原則。

- 建立可以指派給個別使用者的用戶端版本原則。

> [!NOTE]
> 由於匿名使用者不會與使用者、網站或服務產生關聯，因此匿名使用者只會受全域層級的原則影響。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。

- **新增功能** 您可以建立下列一或多個用戶端版本原則：

  - 網站原則

  - 集區原則

  - 使用者原則

- **編輯** 您可以變更任何用戶端版本原則的選項。 使用此選項，您可以執行下列作業：

  - **顯示詳細資料** 此選項會開啟對話方塊，您可以在其中變更用戶端版本原則的選項。

  - **全選** 此選項會選取清單中的所有用戶端版本原則。

  - **刪除** 此選項會刪除所有選取的用戶端版本原則。

- **刷新** 您可以重新整理用戶端版本原則清單，以確認所有用戶端版本原則的選項狀態。

如需用戶端與用戶端版本之間的互用性相關詳細資訊，請參閱規劃檔中的 [用戶端互通性](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) 。 如需使用用戶端版本原則的詳細資訊，請參閱操作文件中的＜[Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013)＞。