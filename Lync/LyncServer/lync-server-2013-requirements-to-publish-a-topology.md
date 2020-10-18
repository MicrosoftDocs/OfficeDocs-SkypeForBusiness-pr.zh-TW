---
title: Lync Server 2013：發行拓撲的需求
description: Lync Server 2013：發行拓撲的需求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5699657e680b78587b8ba354e9dc538f2e280c56
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577859"
---
# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a>在 Lync Server 2013 中發行拓撲的需求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

本主題說明使用拓撲產生器或 Lync Server 2013 管理命令介面命令列介面，發佈拓撲特有的基礎結構和軟體需求。 這些需求是除了適用于所有 Lync Server 2013 系統管理工具的一般作業系統、軟體和許可權要求之外。 在發行拓撲之前，請務必先滿足所有的系統管理工具需求。

  - 您必須在已加入的電腦上，執行拓撲產生器，以加入您所建立之 Lync Server 2013 部署的相同網域或樹系，以便 Active Directory 網域服務準備步驟已經完成，讓您能夠在該電腦上使用系統管理工具，以順利發行您的拓撲。

  - 拓撲中定義的電腦必須加入網域，而不是 Edge Server 和 AD DS 中。 不過，當您發佈拓撲時，電腦不需要線上。

  - 您必須建立集區的檔案共用，並可供遠端使用者使用。

  - 為了發佈 Enterprise Edition 前端集區，SQL Server 型後端伺服器必須加入您要在其中部署伺服器的網域，線上，並以適當的防火牆規則加以設定，讓遠端使用者可以使用該伺服器。 如需指定防火牆例外狀況的詳細資訊，請參閱 [瞭解 SQL Server 的防火牆需求（含 Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md)）。 如需有關設定 SQL Server 的其他詳細資訊，請參閱 [CONFIGURE Sql Server For Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md)。
    
    <div>
    

    > [!NOTE]  
    > Standard Edition server 具有可接受發佈設定的組合資料庫。 您必須先在 Lync Server 部署嚮導中執行 [ <STRONG>準備第一個 Standard Edition server</STRONG> 安裝程式] 工作。

    
    </div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中發佈拓撲](lync-server-2013-publish-the-topology.md)  
[在 Lync Server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)  


[Lync Server 2013 中的系統管理工具軟體需求](lync-server-2013-administrative-tools-software-requirements.md)  
[Lync Server 2013 中的伺服器和工具作業系統支援](lync-server-2013-server-and-tools-operating-system-support.md)  


[安裝和管理 Lync Server 2013 時所需的系統管理員許可權](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

