---
title: Lync Server 2013：準備網域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing domains
ms:assetid: 8eea541c-5f9d-4afc-92a8-a31d6f742544
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398721(v=OCS.15)
ms:contentKeyID: 48184816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c1f5693a14084627d20ae66fa6ec85f6b6c6c6f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-domains-for-lync-server-2013"></a>針對 Lync Server 2013 準備網域

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-29_

[網域準備] 是為 Lync Server 2013 準備 Active Directory 網域服務的最後一個步驟。 [網域準備] 步驟會將必要的存取控制專案（Ace）新增至通用群組，以便在網域中授與主機及管理使用者的許可權。 [網域準備] 會在網域根目錄和三個內建容器中建立 Ace：使用者、電腦及網網域控制站。

您可以在要部署 Lync Server 的網域中的任何電腦上執行網域準備。 您必須準備將主持 Lync Server 或使用者的每個網域。

如果已停用許可權繼承，或在您的組織中停用驗證的使用者許可權，您必須在網域準備期間執行其他步驟。 如需詳細資訊，請參閱[在 Lync Server 2013 中準備鎖定的 Active Directory 網域服務](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)。

如果您的組織使用組織單位（OU），而不是三個內建的容器（也就是使用者、電腦及網網域控制站），則您必須授與已驗證使用者群組的 Ou 讀取權限。 網域準備必須具備容器的讀取權。 如果 [經過驗證的使用者] 群組沒有 OU 的讀取存取權，請執行**CsOuPermission** Cmdlet，如下列程式碼範例所示，以授與每個 OU 的讀取權限。

   ```
    Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU > 
   ```

   ```
    Grant-CsOuPermission -ObjectType "user","contact",inetOrgPerson" -OU "ou=Redmond,dc=contoso,dc=net"
   ```

如需**授權 CsOuPermission** Cmdlet 的詳細資訊，請參閱 Lync Server 管理命令介面檔。

<div class="">


> [!TIP]  
> 如需在網域根目錄和 [使用者]、[電腦] 和 [網網域控制站] 容器中建立之 Ace 的詳細資料，請參閱<A href="lync-server-2013-changes-made-by-domain-preparation.md">Lync Server 2013 中的 [由網域準備所做的變更</A>]。



</div>

<div>

## <a name="in-this-section"></a>本節內容

  - [為 Lync Server 2013 執行網域準備](lync-server-2013-running-domain-preparation.md)

  - [將 Cmdlet 用於 Lync Server 2013 的反向網域準備](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

