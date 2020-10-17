---
title: 移轉撥入存取號碼
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bc96ef027d63c5d2020bd52d55f378fcf7dacf51
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503520"
---
# <a name="migrate-dial-in-access-numbers"></a>移轉撥入存取號碼

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-26_

若要遷移撥入存取號碼，需要兩個步驟：執行 **Import-CsLegacyConfiguration** Cmdlet (在匯 [入原則和設定](import-policies-and-settings.md) 中完成，) 遷移撥號對應表及其他撥入存取號碼設定，以及執行 **Move-CsApplicationEndpoint** 指令程式以遷移連絡人物件。

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>移轉撥入存取號碼

1.  開啟 Office 通訊伺服器 2007 R2 系統管理工具。

2.  在主控台樹狀目錄中，以滑鼠右鍵按一下樹系節點，並依序按一下 **[內容]** 和 **[會議服務員內容]**。

3.  在 **[存取電話號碼]** 索引標籤上，按一下 **[由集區服務]**，依據其相關聯的集區排序存取電話號碼，並識別所移轉之集區的所有存取號碼。

4.  若要識別每個存取號碼的 SIP URI，請按兩下存取號碼來開啟 **[編輯會議服務員號碼]** 對話方塊，然後查看 **[SIP URI]** 下方的內容。

5.  開啟 Lync Server 管理命令介面。

6.  若要將每個撥入存取號碼移至在 Lync Server 2013 上主控的集區，請執行：
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  在 [Office 通訊伺服器 2007 R2 系統管理工具] 的 [ **存取電話號碼** ] 索引標籤上，確認您要遷移的 Office 通訊伺服器 2007 R2 集區沒有任何撥入存取號碼。

</div>

</div>

<span> </span>

</div>

</div>

</div>

