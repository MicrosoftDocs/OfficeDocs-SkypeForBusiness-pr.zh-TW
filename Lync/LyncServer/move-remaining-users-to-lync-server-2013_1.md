---
title: 將剩餘使用者移到 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 0eb990f0-f720-47a7-aaee-437fbd4c4c33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687968(v=OCS.15)
ms:contentKeyID: 49733554
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a728afae37c2e8d317cd6c75872c75d358226475
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>將剩餘使用者移到 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-26_

您可以使用 Lync Server [控制台] 或 [Lync Server 管理命令介面]，將使用者移至新的 Lync Server 2013 部署。 您必須符合一些需求，才能確保順利轉換至 Lync Server 2013。 如需有關完成本主題中程式的先決條件的詳細資訊，請參閱[設定要遷移的用戶端](configure-clients-for-migration_1.md)。 如需有關移動使用者的詳細步驟，請參閱[階段6：將使用者移至試驗](phase-6-move-users-to-the-pilot-pool.md)區。

<div>


> [!IMPORTANT]  
> 您無法使用 Active Directory 使用者和電腦的管理單元或 Microsoft Office 通訊伺服器 2007 R2 管理工具，將使用者從您的舊版環境移至 Lync Server 2013。



</div>

<div>


> [!IMPORTANT]  
> <STRONG>CsLegacyUser</STRONG> Cmdlet 需要正確地形成使用者名稱，且沒有前導或尾部空格。 如果使用者帳戶包含前置或尾部空格，就無法使用<STRONG>CsLegacyUser</STRONG> Cmdlet 移動。



</div>

當您將使用者移至 Lync Server 2013 池時，使用者的資料會移至與新的資料庫池相關聯的後端資料庫。

<div>


> [!IMPORTANT]  
> 這包括舊版使用者建立的作用中會議。 例如，如果舊版使用者已設定「我的<STRONG>會議</STRONG>會議，則在使用者移動之後，仍可在新的 Lync Server 2013 池中提供該會議。 存取該會議的詳細資料仍會是相同的<STRONG>會議 URL 與會議 ID</STRONG>。 唯一的差異在於，該會議現在已託管在 Lync Server 2013 池中，而不是在 Office 通訊伺服器 2007 R2 池中。



</div>

<div>


> [!NOTE]  
> 在 Lync Server 2013 上託管使用者並不需要您同時部署已升級的用戶端。 只有在使用者升級至新的用戶端軟體時，才能使用新的功能。



</div>

<div>

## <a name="post-migration-task"></a>遷移後任務

1.  在您移動使用者之後，請確認指派給他們的會議原則。

2.  若要確保由駐留在 Lync Server 2013 的使用者所組織的會議能與駐留在 Office 通訊伺服器 2007 R2 的同盟使用者順暢運作，指派給已遷移使用者的會議原則應該允許匿名參與者。

3.  允許匿名參與者的會議原則**允許參與者邀請**lync server 2013 [控制台] 中選取的匿名使用者，並在 Lync Server 管理命令介面的 [ **CsConferencingPolicy** ] Cmdlet 的輸出中，將**AllowAnonymousParticipantsInMeetings**設為**True** 。

4.  如需使用 Lync Server 管理命令介面設定會議原則的詳細資訊，請參閱 Lync Server 管理命令介面檔中的[設定 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

