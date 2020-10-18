---
title: 'Lync Server 2013：事先要求憑證 (選用) '
description: Lync Server 2013：預先要求憑證 (選用) 。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d92ac9b68012487d07f25f08649689611117202
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579029"
---
# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a>在 Lync Server 2013 的預先 (選用) 中預先要求憑證

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-02-21_

所有執行 Lync Server 2013 的內部伺服器都必須有憑證，包含每個 Enterprise Edition 前端伺服器、Standard Edition Server、Director、Edge Server 和獨立轉送伺服器。 雖然建議內部伺服器使用內部企業憑證授權單位 (CA)，但您也可以使用公用 CA。 如需憑證需求的詳細資訊，以及使用公用 CA，請參閱規劃檔中的 [Lync Server 2013 內部伺服器的憑證需求](lync-server-2013-certificate-requirements-for-internal-servers.md) 。

Lync Server 2013 安裝套裝程式含憑證嚮導，可協助在部署期間要求、指派及安裝憑證的工作。 如果您想要在安裝伺服器之前要求憑證 (例如，若要在實際部署伺服器期間節省時間) ，您可以使用已安裝 Lync Server 2013 系統管理工具的電腦或組織中所定義的憑證要求程式，來做到這一點，只要您確定憑證是可匯出的，且包含所有必要的主體替代名稱。 事先要求憑證是選用的。 如果您未預先要求，您必須在需要憑證的每一部伺服器安裝時，要求他們。

此部署檔提供使用憑證嚮導要求憑證的程式，做為安裝程式的一部分，如在 [lync server 2013 中設定伺服器的憑證](lync-server-2013-configure-certificates-for-servers.md)中所述，在 [lync server 2013 中設定 Director 的憑證](lync-server-2013-configure-certificates-for-the-director.md)，並在此部署檔的 [Lync server 2013 區段中安裝轉送伺服器的](lync-server-2013-install-the-files-for-mediation-server.md) 檔案。 如果您事先要求憑證，則必須在這些區段中修改憑證部署程式，視需要將憑證匯入與指派，而不是在部署時要求。

<div>


> [!NOTE]  
> Lync Server 2013 支援 SHA-256 憑證，以用於來自執行 Windows Vista、Windows Server &nbsp; 2008、Windows server &nbsp; 2008 &nbsp; R2 和 Windows 7 作業系統，以及 Lync Phone Edition 之用戶端的連線。 為了支援使用 SHA-256 的外部存取，外部憑證由公用 CA 使用 SHA-256 發行。



</div>

</div>

<span> </span>

</div>

</div>

</div>

