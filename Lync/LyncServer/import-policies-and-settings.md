---
title: 匯入原則及設定
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b12a47ffde7d09fa7e216312211b6f0118b89233
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037383"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a>匯入原則及設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012年-09-28_

Office Communications Server 2007 R2 拓撲資訊與 Lync Server 2013 試驗集區合併後，您需要執行 Lync Server 2013 管理命令介面 cmdlet 以將您的 Office Communications Server 2007 R2 原則與組態設定移轉至 Lync Server 2013 試驗集區。

**Import-cslegacyconfiguration** cmdlet 匯入原則、 語音路由、 撥號對應表、 Communicator Web Access Url，以及撥入存取號碼給 Lync Server 2013。

<div>

## <a name="to-migrate-policies-and-settings"></a>移轉原則與設定

1.  Lync Server 2013 前端伺服器上，啟動 Lync Server 管理命令介面。

2.  在命令列輸入下列命令：
    
        Import-CsLegacyConfiguration
    
    匯入原則之後，使用下列程序以查看 Lync Server Control Panel 中匯入的原則。

</div>

<div>

## <a name="to-view-imported-policies"></a>檢視匯入的原則

1.  開啟 Lync Server 2013 控制台。

2.  按一下 [語音路由]****，然後檢視匯入的原則。

3.  按一下 [會議]****，然後檢視匯入的原則。

4.  按一下 [**同盟和外部存取**，然後檢視匯入的原則。

5.  按一下 [監控和封存]****，然後檢視匯入的原則。

</div>

</div>

<span> </span>

</div>

</div>

</div>

