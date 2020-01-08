---
title: Lync Server 2013：預先要求憑證 (選用)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6b376a2c1652dcaf255e39f6d112568b7c3bf31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>針對 Lync Server 2013 預先要求憑證 (選用)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

所有執行 Lync Server 2013 的內部伺服器都需要有憑證，包括每個企業版前端伺服器、標準版伺服器、控制器、邊緣伺服器以及獨立的中繼伺服器。 雖然建議內部伺服器使用內部企業憑證授權單位（CA），但是您也可以使用公用 CA。 如需有關證書需求以及公用 CA 用途的詳細資料，請參閱規劃檔中的[Lync Server 2013 內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md)。

Lync Server 2013 安裝套裝程式含 [憑證] 嚮導，可協助您在部署期間要求、指派及安裝憑證的工作。 如果您想要在安裝伺服器之前要求憑證（例如，在實際部署伺服器期間節省時間），您可以使用安裝 Lync Server 2013 系統管理工具的電腦或使用憑證申請來執行此操作。您組織中定義的程式，只要確認憑證是可匯出的，且包含所有必要的主體替換名稱即可。 事先要求憑證是選用的。 如果您沒有提前要求，您必須在需要憑證的每個伺服器設定中要求它們。

此部署檔提供使用 [憑證] 嚮導來要求認證的程式，以作為設定程式的一部分，如在 lync server 2013 的 [[為伺服器設定憑證](lync-server-2013-configure-certificates-for-servers.md)] 中所述，請在[lync server 2013 中設定主管的憑證](lync-server-2013-configure-certificates-for-the-director.md)，然後在此部署檔的[Lync Server 2013 區段中安裝轉送伺服器](lync-server-2013-install-the-files-for-mediation-server.md)的檔案。 如果您提前申請憑證，您必須在那些區段中修改憑證部署程式，視需要在部署時，將憑證匯入並指派給證書。

<div>


> [!NOTE]  
> Lync Server 2013 支援從執行 Windows Vista、Windows Server&nbsp;2008、Windows Server&nbsp;2008&nbsp;R2 及 Windows 7 作業系統及 Lync Phone EDITION 的用戶端連線的 SHA-256 憑證支援。 若要使用 SHA-256 支援外部存取，外部憑證是由使用 SHA-256 的公用 CA 所頒發。



</div>

</div>

<span> </span>

</div>

</div>

</div>

