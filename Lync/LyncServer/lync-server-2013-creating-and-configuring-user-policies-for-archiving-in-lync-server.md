---
title: 在 Lync Server 中建立及設定用於存檔的使用者原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating and configuring user policies for Archiving in Lync Server
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204923(v=OCS.15)
ms:contentKeyID: 48184234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb4385d219173ca33ae7120dcf3e9d75d4c65f14
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756947"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-and-configuring-user-policies-for-archiving-in-lync-server-2013"></a>在 Lync Server 2013 中建立及設定用於存檔的使用者原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-09_

若要針對駐留在 Lync Server 上的特定使用者啟用或停用封存，您必須先建立使用者原則，然後將原則套用至一或多個使用者或使用者群組。 如需將使用者原則套用到特定使用者和使用者群組的詳細資料，請參閱在部署檔中將[Lync Server 存檔原則套用至 Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)中的使用者。

如需有關歸檔原則運作方式的詳細資料，包括全域、網站和使用者原則的階層，請參閱在規劃檔中、部署檔或作業檔中的[存檔在 Lync Server 2013 中的運作方式](lync-server-2013-how-archiving-works.md)。

<div>


> [!NOTE]
> 如果您已針對您的部署啟用 Microsoft Exchange 整合，Exchange 就地保留原則會控制是否針對託管于 Exchange 2013 的使用者啟用封存，並將其信箱放在就地保留中。 如需詳細資訊，請參閱在部署檔中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 整合時，在 Lync Server 2013 中設定存檔原則</A>。<BR>在啟用封存前，您應該先在封存配置中指定所有適當的選項。 如需詳細資訊，請參閱部署檔中的<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013</A>中的 [設定封存選項]。



</div>

<div>

## <a name="to-configure-an-archiving-policy-for-users-homed-on-lync-server"></a>針對駐留在 Lync Server 的使用者設定存檔原則

1.  從指派給 CsArchivingAdministrator 或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server 2013 [控制台]。 如需可用於啟動 Lync Server 2013 [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**監視及**封存]，然後按一下 [封存**原則**]。

4.  依序按一下 [新增]**** 和 [使用者原則]****。

5.  在**新**的 [封存原則] 中，執行下列動作：
    
      - 在 [**名稱**] 中，指定使用者原則的名稱。
    
      - 在 [**描述**] 中，提供使用者原則的相關資訊（例如，法律部門的使用者原則）。
    
      - 若要控制使用者原則的內部通訊的歸檔，請選取或清除 [封存**內部通訊**] 核取方塊。
    
      - 若要控制使用者原則的外部通訊的存檔，請選取或清除 [封存**外部通訊**] 核取方塊。

6.  按一下 [認可]****。

使用者原則只適用于您指派原則的使用者。 如需將使用者原則套用到特定使用者的詳細資料，請參閱在部署檔中將[Lync Server 存檔原則套用至 Lync server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)中的使用者。

</div>

</div>

<span> </span>

</div>

</div>

</div>

