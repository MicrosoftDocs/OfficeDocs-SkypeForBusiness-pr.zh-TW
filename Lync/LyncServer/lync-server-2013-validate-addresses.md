---
title: Lync Server 2013：驗證位址
description: Lync Server 2013：驗證位址。
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
ms.openlocfilehash: bcbb8789912b3bcbcfb60dd79807f06c2957c1f6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547269"
---
# <a name="validate-addresses-in-lync-server-2013"></a>在 Lync Server 2013 中驗證位址

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-17_

在發佈位置資料庫之前，您必須對照主要街道通訊指南 (MSAG) （由 SIP 主幹或公用交換電話網路 (PSTN) E9-1-1 服務提供者所維護）驗證新的位置。

如需 SIP 主幹 E9-1-1 服務提供者的詳細資訊，請參閱 [選擇 E9-1-1 服務提供者以進行 Lync Server 2013](lync-server-2013-choosing-an-e9-1-1-service-provider.md)。

如需驗證位址的詳細資訊，請參閱 Lync Server 管理命令介面檔中的下列 Cmdlet：

  - **CsLisServiceProvider**

  - **CsLisServiceProvider**

  - **Remove-CsLisServiceProvider**

  - **CsLisCivicAddress**

  - **Test-CsLisCivicAddress**

<div>

## <a name="to-validate-addresses-located-in-the-location-database"></a>驗證位於位置資料庫中的位址

1.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

2.  執行下列 Cmdlet 以設定緊急服務提供者連線。
    
        $pwd = Read-Host -AsSecureString <password>
        Set-CsLisServiceProvider -ServiceProviderName Provider1 -ValidationServiceUrl <URL provided by provider> -CertFileName <location of certificate provided by provider> -Password $pwd

3.  執行下列 Cmdlet 來驗證位置資料庫中的位址。
    
        Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus
    
    您也可以使用 **Test-CsLisCivicAddress** Cmdlet 來驗證個別的位址。

</div>

</div>

<span> </span>

</div>

</div>

</div>

