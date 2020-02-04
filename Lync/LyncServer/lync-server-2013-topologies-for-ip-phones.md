---
title: Lync Server 2013： IP 手機的拓撲
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies for IP phones
ms:assetid: 26ebffcf-43ff-4e70-847d-0fbc90e94e57
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425740(v=OCS.15)
ms:contentKeyID: 48183662
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e05a56d30167f2e20a383cde9fcfaaa70418e650
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-for-ip-phones-in-lync-server-2013"></a>Lync Server 2013 中的 IP 手機拓撲

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-21_

本節概述連接程式，並說明 IP 電話在內部和外部網路中的連線方式之間的差異。

<div>


> [!NOTE]  
> Lync Server 提供下列 IP 電話支援： Aastra 6721ip 常見區域手機、Aastra 6725ip phone、HP 4110 IP Phone （通用區域電話）、HP 4120 IP phone （常見地區電話）、Polycom CX600 IP Phone （電話機），以及 Polycom CX700 ip 電話機、Polycom CX500 IP常見的區域電話，以及 Polycom CX3000 IP 會議電話。 在這些手機中，除了 Polycom CX700 之外，所有人都可以執行 Lync Phone Edition。



</div>

下圖說明公司環境中所有裝置連線所涉及的元件。

**內部拓朴**

![3d88893e-df57-46e3-855a-a1d24589030a](images/Gg425740.3d88893e-df57-46e3-855a-a1d24589030a(OCS.15).jpg "3d88893e-df57-46e3-855a-a1d24589030a")

<div>


> [!NOTE]  
> 上圖是邏輯標記法，不是物理概覽。 例如，Active Directory 網域服務（AD DS）很少位於與任何 Lync Server 元件相同的電腦上。 使用者存放區可以位於後端伺服器或 [封存與監視伺服器] 上。 Lync Server 管理命令介面、web 伺服器及更新服務全都是前端伺服器角色的一部分。



</div>

下圖提供裝置位於公司網路以外時所涉及元件的概覽。

**外部拓撲**

![8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3](images/Gg425740.8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3(OCS.15).jpg "8ce6bb8e-b89c-4c4e-ac6d-41ac6c68f6f3")

<div>


> [!NOTE]  
> 裝置更新 Web 服務提供外部與內部網站，但此處只顯示外部網站。<BR>如果要啟用外部存取，則必須在 DNS 中發佈註冊機構的裝置更新 Web 服務的位置和 URL。 此外，還必須部署並正確設定 Edge 伺服器，才能允許從裝置到公司環境的外部通訊和返回。 這會在前一個圖表中省略，因為 Edge 部署不是特定于裝置連線性的。



</div>

</div>

<span> </span>

</div>

</div>

</div>

