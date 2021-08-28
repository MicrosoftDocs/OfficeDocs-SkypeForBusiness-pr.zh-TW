---
title: 用戶端版本原則建立新的或編輯現有
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientCVPolicyEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e32c6712-6dc9-4de9-8d74-9fdccf3de1ba
description: 您可以指定環境中支援的用戶端版本。 當執行不同版本的兩個用戶端互動時，這兩個用戶端可用的功能會受限於彼此的功能。 若要充分運用商務用 Skype Server 2015 所包含的功能，並改善整體使用者體驗，您可以使用用戶端版本篩選器來限制環境中所用的用戶端版本。 使用用戶端版本篩選器還可幫助您降低支援多個用戶端版本的相關成本。
ms.openlocfilehash: 98eb19a9c59d21f34864edf37cb61af79d8c5454
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608260"
---
# <a name="client-version-policy-create-new-or-edit-existing"></a>用戶端版本原則：建立新的或編輯現有原則

您可以指定環境中支援的用戶端版本。 當執行不同版本的兩個用戶端互動時，這兩個用戶端可用的功能會受限於彼此的功能。 若要充分運用商務用 Skype Server 2015 所包含的功能，並改善整體使用者體驗，您可以使用用戶端版本篩選器來限制環境中所用的用戶端版本。 使用用戶端版本篩選器還可幫助您降低支援多個用戶端版本的相關成本。

> [!IMPORTANT]
> 篩選依優先順序順序列出。 例如，如果您有一個篩選器，可讓執行1.5 版本的用戶端進行連線，接著會封鎖執行高於2.0 之版本之用戶端的篩選器，第一個篩選器優先，而且執行版本為1.5 的用戶端可以進行連接。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「 **新增用戶端版本原則** 」或「 **編輯用戶端版本原則** 」頁面上執行下列工作：

- 新增或修改用戶端版本原則的名稱或描述。

- 新增或修改用戶端版本原則的用戶端版本規則。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。

- **範圍** 識別用戶端版本原則的範圍 (網站、集區或使用者) 。

- **名稱** 您可以新增或修改用戶端版本原則的名稱。

- **描述** 您可以新增描述，以協助識別「用戶端版本原則」頁面之清單中的原則。

- **新** 您可以將新的用戶端版本規則新增至原則。

- **顯示詳細資料** 此選項會開啟對話方塊，您可以在其中變更用戶端版本規則的選項。

- **移除** 此選項會從原則中移除選取的用戶端版本規則。

- **向上及向中箭** 號此選項會以優先順序向上或向內移動選取的用戶端版本規則。 規則會依照所列順序進行處理。

如需用戶端和用戶端版本間互通性的詳細資訊，請參閱規劃文件中的＜[Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)＞。如需使用用戶端版本原則的詳細資訊，請參閱操作文件中的＜[Specify the Client Versions Supported in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013)＞。