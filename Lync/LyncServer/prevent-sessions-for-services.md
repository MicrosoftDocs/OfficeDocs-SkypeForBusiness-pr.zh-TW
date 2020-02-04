---
title: 防止服務的工作階段
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf8fb96fef5a01f9b25ca954dd27d1bdfd1f7055
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a>防止服務的工作階段

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-04_

您可以使用 Microsoft Lync Server 2010 [控制台] 來避免在特定電腦上執行的所有 Lync Server 2010 服務的新會話，或避免特定 Lync Server 2010 服務的新會話。

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a>避免電腦上所有 Lync Server 服務的新會話

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟 [Lync Server 控制台]。

3.  在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。

4.  在 [**狀態**] 頁面上，視需要排序或搜尋清單，以尋找執行您想要防止新會話之服務的電腦，然後按一下該電腦。

5.  按一下 [**動作**]。

6.  按一下 [**防止所有服務的新會話**]。

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a>若要防止特定服務的新會話

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟 [Lync Server 控制台]。

3.  在左側導覽列中，按一下 [**拓撲**]，然後按一下 [**狀態**]。

4.  在 [**狀態**] 頁面上，視需要排序或搜尋清單，以尋找執行您要開始或停止之服務的電腦，然後按一下它。

5.  按一下 [**屬性**]。

6.  如有需要，請排序服務清單，然後按一下您要防止新會話的服務。

7.  按一下 [**動作**]。

8.  按一下 [**避免新的服務會話**]。

9.  按一下 [**關閉**]。

</div>

</div>

<span> </span>

</div>

</div>

</div>

