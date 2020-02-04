---
title: 匯入原則和設定
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
ms.openlocfilehash: 6f8023f917e3da6757ce27ede44a63cf0ab1a08d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="import-policies-and-settings"></a>匯入原則和設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-28_

在您將 Office 通訊伺服器 2007 R2 拓撲資訊與 Lync Server 2013 試驗池合併之後，您必須執行 Lync Server 2013 管理命令介面 Cmdlet，以遷移您的 Office 通訊伺服器 2007 R2 原則和設定設定移至您的 Lync Server 2013 試生產池。

匯**入-CsLegacyConfiguration** Cmdlet 會將原則、語音路由、撥號方案、Communicator Web Access url，以及撥入存取號碼匯入 Lync Server 2013。

<div>

## <a name="to-migrate-policies-and-settings"></a>遷移原則和設定

1.  在 Lync Server 2013 前端伺服器上，啟動 Lync Server 管理命令介面。

2.  在命令列中，輸入下列內容：
    
        Import-CsLegacyConfiguration
    
    匯入原則之後，請使用下列程式，查看 Lync Server 控制台中的匯入原則。

</div>

<div>

## <a name="to-view-imported-policies"></a>若要查看匯入的原則

1.  開啟 Lync Server 2013 [控制台]。

2.  按一下 [**語音路由**] 並查看已匯入的原則。

3.  按一下 [**會議**] 並查看已匯入的原則。

4.  按一下 [**同盟與外部存取**] 並查看匯入的原則。

5.  按一下 [**監視及**封存]，然後查看匯入的原則。

</div>

</div>

<span> </span>

</div>

</div>

</div>

