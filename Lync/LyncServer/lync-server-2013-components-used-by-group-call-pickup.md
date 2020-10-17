---
title: Lync Server 2013：群組呼叫收取所使用的元件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 062dc114534abb7d2a011c31b9747c2d6a0a45bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502360"
---
# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a>Lync Server 2013 中群組呼叫收取所使用的元件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2013-01-30_

當您部署企業語音和通話駐留應用程式時，會自動部署群組呼叫收取。 您可以將通話駐留軌道表設定為呼叫收取群組的號碼，然後指派使用者呼叫收取群組，並為使用者啟用群組通話收取，以啟用群組呼叫收取。 下列 Lync Server 元件支援群組呼叫收取：

  - **應用程式服務**    Application service 提供平臺，用來部署、裝載和管理整合通訊應用程式，例如通話駐留應用程式。 應用程式服務會自動安裝在前端集區和每個 Standard Edition server 上的每一部前端伺服器上。

  - **通話駐留應用程式**    通話駐留應用程式是由應用程式服務主控的整合通訊應用程式之一。 群組呼叫收取是以通話駐留應用程式為基礎。

  - **Lync Server 管理命令**     介面您可以使用 Lync Server 管理命令介面來管理群組呼叫收取群組。

  - **SEFAUtil 資源套件工具**    您可以使用 [次要分機] 功能啟用實用程式 (SEFAUtil) 指派使用者至來電收取群組，以及啟用或停用使用者的電話收取。

</div>

<span> </span>

</div>

</div>

</div>

