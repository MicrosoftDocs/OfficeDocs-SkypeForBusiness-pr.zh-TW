---
title: 移轉撥入存取號碼
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: 568a94b7-a697-4ab2-9008-dc9ecc1c87c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204898(v=OCS.15)
ms:contentKeyID: 48184171
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b86db6e669fd5f52827591c25e5bb237bd9ee012
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975465"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a>移轉撥入存取號碼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-26_

遷移撥入存取號碼需要兩個步驟：執行**CsLegacyConfiguration** Cmdlet （在 [匯[入原則和設定](import-policies-and-settings.md)] 中完成），以遷移撥號方案及其他撥入存取號碼設定，並執行**移動 CsApplicationEndpoint** Cmdlet 來遷移連絡人物件。

<div>

## <a name="to-migrate-dial-in-access-numbers"></a>若要遷移撥入存取號碼

1.  開啟 Office 通訊伺服器 2007 R2 管理工具。

2.  在主控台樹中，以滑鼠右鍵按一下 [林] 節點，按一下 [**屬性**]，然後按一下 [**會議助理屬性**]。

3.  在 [**存取電話號碼**] 索引標籤上，按一下 [**依資源庫提供服務**]，依相關聯的池排序存取電話號碼，並找出您要從中遷移之池的所有存取號碼。

4.  若要識別每個存取號碼的 SIP URI，請按兩下存取號碼以開啟 [**編輯會議助理編號**] 對話方塊，然後查看 [ **SIP URI**]。

5.  開啟 Lync Server 管理命令介面。

6.  若要將每個撥入存取號碼移至 Lync Server 2013 上託管的池，請執行：
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

7.  在 Office 通訊伺服器 2007 R2 管理工具的 [**存取電話號碼**] 索引標籤上，確認您要從中遷移的 Office 通訊伺服器 2007 R2 池不會保留撥入存取號碼。

</div>

</div>

<span> </span>

</div>

</div>

</div>

