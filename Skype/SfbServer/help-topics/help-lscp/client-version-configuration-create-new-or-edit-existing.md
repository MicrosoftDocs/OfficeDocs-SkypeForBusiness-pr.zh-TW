---
title: 用戶端版本設定建立新的或編輯現有
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
- ms.lync.lscp.ClientCVSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 07fec57c-5cd3-422a-829a-0b62cb0092c4
description: 用戶端版本設定的設定可用來開啟或關閉用戶端版本控制。 全域用戶端版本設定會以商務用 Skype 伺服器進行安裝，並可用來啟用或停用整個伺服器部署的用戶端版本控制。 啟用全域設定時，所有既有的用戶端版本原則都會在使用者嘗試登入時生效。 若不想要執行用戶端版本控制，可以停用全域用戶端版本設定。
ms.openlocfilehash: 173bd8d2eb7ca47811497e07b8824aff6a4e6a20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095627"
---
# <a name="client-version-configuration-create-new-or-edit-existing"></a>用戶端版本組態：建立新的或編輯現有

用戶端版本設定的設定可用來開啟或關閉用戶端版本控制。 全域用戶端版本設定會以商務用 Skype 伺服器進行安裝，並可用來啟用或停用整個伺服器部署的用戶端版本控制。 啟用全域設定時，所有既有的用戶端版本原則都會在使用者嘗試登入時生效。 若不想要執行用戶端版本控制，可以停用全域用戶端版本設定。

您也可以建立網站專用的用戶端版本設定，讓您能夠依網站啟用或停用用戶端版本控制。網站專用的設定優先於全域設定。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「新的用戶端版本設定」或「編輯用戶端版本設定」頁面上執行下列工作：

- 新增或修改用戶端版本設定的名稱。

- 啟用或停用全域或特定網站的用戶端版本控制。

- 新增或修改用戶端版本設定的預設動作。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。


- **範圍** 識別用戶端版本設定 (全域或網站) 的範圍。

- **名稱** 您可以新增或修改用戶端版本設定的名稱。

- **啟用版本控制** 您可以啟用或停用全域或網站的用戶端版本控制，視設定的範圍而定。

- **預設動作** 您可以選取當使用者嘗試使用沒有特定用戶端版本原則的用戶端應用程式登入時，將會套用的預設動作。 您有下列選項：

  - **允許** 當用戶端版本不符合用戶端版本原則清單中的任何篩選準則時，允許用戶端登入。

  - **封鎖** 當用戶端版本不符合用戶端版本原則清單中的任何篩選準則時，禁止用戶端登入。

  - **使用 URL 的封鎖** 當用戶端版本不符合用戶端版本原則清單中的任何篩選準則時，禁止用戶端登入，並包含錯誤訊息，其中包含可下載更新的用戶端 URL。

  - **允許搭配 URL** 當用戶端版本不符合用戶端版本原則清單中的任何篩選準則時，允許用戶端登入，並包含包含 URL 的錯誤訊息，可供下載更新的用戶端。

  - **URL** 如果您選取 [ **封鎖 WITH url** ] 或 [ **允許搭配 url**]，您可以指定要包含在錯誤訊息中的用戶端下載 URL。

如需用戶端和用戶端版本間互通性的詳細資訊，請參閱規劃文件中的＜[Client Interoperability in Lync 2013 Preview](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013)＞。 如需使用用戶端版本設定的詳細資訊，請參閱作業文件中的＜[Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)＞。