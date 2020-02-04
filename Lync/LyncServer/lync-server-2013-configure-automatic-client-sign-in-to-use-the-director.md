---
title: Lync Server 2013：設定用戶端自動登入以使用 Director
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a6d9090796b2c6c2271025ed4d17a134943c11
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757797"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a>在 Lync Server 2013 中設定用戶端自動登入以使用 Director

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-08_

當您部署 Lync Server 2013、主管或控制器池時，建議您使用自動用戶端登入做為最佳做法。 如需有關如何設定 DNS 伺服器以進行自動用戶端登入的詳細資料，請參閱規劃檔中的[Lync Server 2013 中的自動用戶端登入的 DNS 需求](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)。

如果您已經部署了自動用戶端登入，請參閱下列各節，以在您的主管上進行設定。

<div>

## <a name="single-director-instance"></a>單一控制器實例

如果您已部署自動用戶端登入，且它指向前端伺服器或前端池，您必須將 DNS SRV 記錄變更為指向控制器。

</div>

<div>

## <a name="director-pool"></a>主管池

如果您已部署自動用戶端登入，且它指向前端伺服器或頂層端池，您必須將 DNS SRV 記錄變更為指向主管池。

</div>

</div>

<span> </span>

</div>

</div>

</div>

