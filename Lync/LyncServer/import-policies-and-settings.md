---
title: 匯入原則及設定
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Import policies and settings
ms:assetid: b25decee-2ee5-4836-b370-454411d39252
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205178(v=OCS.15)
ms:contentKeyID: 48185147
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1163a8abc54f60d55f1042d6d82552ca9f133a60
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523390"
---
# <a name="import-policies-and-settings"></a>匯入原則及設定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

在您將 Office 通訊伺服器 2007 R2 拓撲資訊與您的 Lync Server 2013 試驗集區合併之後，您必須執行 Lync Server 2013 管理命令介面 Cmdlet，將您的 Office 通訊伺服器 2007 R2 原則和設定值遷移至 Lync Server 2013 試驗集區。

**Import-CsLegacyConfiguration** Cmdlet 會將原則、語音路由、撥號對應表、Communicator Web Access URLs 和撥入存取號碼匯入 Lync Server 2013。

<div>

## <a name="to-migrate-policies-and-settings"></a>移轉原則與設定

1.  在 Lync Server 2013 前端伺服器上，啟動 Lync Server 管理命令介面。

2.  在命令列輸入下列命令：
    
        Import-CsLegacyConfiguration
    
    在匯入原則之後，請使用下列程式，在 Lync Server [控制台] 中查看匯入的原則。

</div>

<div>

## <a name="to-view-imported-policies"></a>檢視匯入的原則

1.  開啟 [Lync Server 2013 控制台]。

2.  按一下 [語音路由]****，然後檢視匯入的原則。

3.  按一下 [會議]****，然後檢視匯入的原則。

4.  按一下 [ **同盟和外部存取** ]，然後查看已匯入的原則。

5.  按一下 [監控和封存]****，然後檢視匯入的原則。

</div>

</div>

<span> </span>

</div>

</div>

</div>

