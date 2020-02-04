---
title: Lync Server 2013：驗證位址
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate addresses
ms:assetid: aae557c9-e6f5-4d23-8af1-1d4cd7968c54
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412808(v=OCS.15)
ms:contentKeyID: 48185108
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 397c1037937e100f1981a689f0860362d852ed10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743803"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-addresses-in-lync-server-2013"></a>驗證 Lync Server 2013 中的位址

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

在發佈位置資料庫之前，您必須針對由 SIP 主幹或公用交換電話網絡（PSTN） E9-1-1 服務提供者維護的主要街道位址指南（MSAG）驗證新的位置。

如需 SIP 幹線 E9-1-1 服務提供者的詳細資料，請參閱[選擇 Lync Server 2013 的 E9 服務提供者](lync-server-2013-choosing-an-e9-1-1-service-provider.md)。

如需驗證位址的詳細資料，請參閱下列 Cmdlet 的 Lync Server 管理命令介面檔：

  - **CsLisServiceProvider**

  - **Set-CsLisServiceProvider**

  - **移除-CsLisServiceProvider**

  - **CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>驗證位於位置資料庫中的位址

1.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列 Cmdlet 來設定緊急服務提供者連線。
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  執行下列 Cmdlet 以驗證位置資料庫中的位址。
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    您也可以使用**Test CsLisCivicAddress** Cmdlet 來驗證個別的位址。

</div>

</div>

<span> </span>

</div>

</div>

</div>

