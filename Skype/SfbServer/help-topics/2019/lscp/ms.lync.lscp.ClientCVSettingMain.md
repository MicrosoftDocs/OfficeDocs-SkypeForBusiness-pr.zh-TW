---
title: 用戶端版本組態
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientCVSettingMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: cb17314e-b89e-4821-8855-12f8fd2edc9b
ROBOTS: NOINDEX, NOFOLLOW
description: 除了指定您要在環境中支援的用戶端版本之外，您也可以針對尚未定義版本原則的用戶端，指定預設動作。 這可讓您限制環境中所使用的用戶端版本，這可協助您控制支援多個用戶端版本的相關成本。
ms.openlocfilehash: 57a999b9300947fc74091852f0729aea91739eae
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761401"
---
# <a name="client-version-configuration"></a>用戶端版本組態

除了指定您要在環境中支援的用戶端版本之外，您也可以針對尚未定義版本原則的用戶端，指定預設動作。 這可讓您限制環境中所使用的用戶端版本，這可協助您控制支援多個用戶端版本的相關成本。

## <a name="tasks-you-can-perform"></a>您可以執行的工作

您可以在「 **用戶端版本** 設定」頁面上執行下列工作：

- 編輯 default ( **Global**) client version configuration。

- 為特定網站建立用戶端版本設定。

- 啟用及停用現有的用戶端版本設定。

> [!NOTE]
> 由於匿名使用者不會與網站產生關聯，因此匿名使用者只會受到全域層級原則的影響。

## <a name="ui-reference"></a>UI 參考

下列清單說明頁面上的功能表、命令、欄位及內容。


- **新** 您可以為特定網站建立用戶端版本設定。

- **編輯** 您可以變更任何用戶端版本原則的選項。 使用此選項，您可以執行下列作業：

  - **顯示詳細資料** 此選項會開啟對話方塊，您可以在其中變更用戶端版本設定的選項。

  - **全選** 此選項會選取清單中的所有用戶端版本設定。

  - **Delete** 此選項會刪除所有選取的用戶端版本設定。

- **Refresh** 您可以重新整理用戶端版本設定清單，以確認所有用戶端版本設定的選項狀態。

如需用戶端與用戶端版本之間的互用性相關詳細資訊，請參閱規劃檔中的 [用戶端互通性](/previous-versions/office/lync-server-2013/lync-server-2013-client-interoperability-in-lync-2013) 。 如需使用用戶端版本設定的詳細資訊，請參閱作業文件中的＜[Modify the Default Action for Clients Not Explicitly Supported or Restricted](/previous-versions/office/lync-server-2013/lync-server-2013-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted)＞。