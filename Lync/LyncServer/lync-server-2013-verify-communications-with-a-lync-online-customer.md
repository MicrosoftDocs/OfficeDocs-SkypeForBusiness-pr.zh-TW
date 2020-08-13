---
title: Lync Server 2013：驗證與 Lync Online 客戶的通訊
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03aae75cfdb3e179347d14c6f42a90ffe060fad7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211879"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a>在 Lync Server 2013 中驗證與 Lync Online 客戶的通訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-08_

若要讓組織中的 Lync 使用者能夠與 Microsoft Lync Online 2010 客戶的使用者進行通訊，您必須完成下列步驟：

  - 符合所有必要條件。 這包括部署您的內部及 edge 伺服器、啟用組織的同盟支援和設定使用者帳戶。 如需詳細資訊，請參閱 [在 Lync Server 2013 中與 Lync Online 客戶進行同盟的必要條件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)。

  - 設定內部部署中的網域存取支援。 這包括建立主機提供者專案及設定您的部署，以允許從 Lync Online 客戶的網域存取。 如需詳細資訊，請參閱 [Configure federation support for a Lync Online domain In Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)。

  - 設定您的使用者帳戶以支援同盟。 如需詳細資訊，請參閱 [Configure user access for 同盟 with a Lync Online 客戶 In Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)。

完成所有這些步驟之後，如果 Lync Online 2010 客戶的所有設定都完成其線上服務的所有設定，以支援與組織的同盟，請測試組織內部使用者與 Lync Online 客戶的使用者之間的通訊，以驗證通訊。 如果通訊不成功，請使用 Edge Server 中的記錄工具來捕獲記錄檔和追蹤檔，以便疑難排解問題。 如需使用記錄工具的詳細資訊，請參閱 Operations 檔中的 [Open Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md) 。 如需有關記錄工具的詳細資訊，請參閱 TechNet 文件庫上的 Lync Server 2010 記錄工具檔 [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) 。

</div>

<span> </span>

</div>

</div>

</div>

