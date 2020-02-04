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
ms.openlocfilehash: f9b20be32ecbc7c3c684009c9c2f928c9dc897cd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a>在 Lync Server 2013 中驗證與 Lync Online 客戶的通訊

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-08_

若要讓貴組織中的 Lync 使用者與 Microsoft Lync Online 2010 客戶的使用者進行通訊，您必須完成下列步驟：

  - 符合所有先決條件。 這包括部署您的內部與邊緣伺服器、啟用貴組織的同盟支援，以及設定使用者帳戶。 如需詳細資訊，請參閱[在 Lync Server 2013 中與 Lync Online 客戶進行聯盟的先決條件](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)。

  - 在內部部署中設定網域存取支援。 這包括建立主機提供者專案並將您的部署設定為允許從 Lync Online 客戶的網域存取。 如需詳細資訊，請參閱[在 Lync Server 2013 中設定 Lync Online 網域的同盟支援](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)。

  - 已將您的使用者帳戶設定為支援同盟。 如需詳細資訊，請參閱[在 Lync Server 2013 中設定與 Lync Online 客戶的同盟的使用者存取權](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)。

完成所有這些步驟之後，Lync Online 2010 客戶的所有設定都完成了其線上服務的所有設定，以支援與貴組織的同盟，請透過測試內部網路間的通訊來驗證通訊貴組織中的使用者，以及 Lync Online 客戶的使用者。 如果通訊失敗，請使用邊緣伺服器的記錄工具來捕獲記錄和追蹤檔案，以便對問題進行疑難排解。 如需使用記錄工具的詳細資料，請參閱在作業檔中[開啟 Lync Server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。 如需記錄工具的詳細資訊，請參閱 TechNet Library 上的 Lync Server 2010 記錄工具檔[http://go.microsoft.com/fwlink/p/?linkId=199265](http://go.microsoft.com/fwlink/p/?linkid=199265)。

</div>

<span> </span>

</div>

</div>

</div>

