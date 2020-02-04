---
title: 將剩餘使用者移到 Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move remaining users to Lync Server 2013
ms:assetid: 72025e1b-97d1-40e9-8a98-28c018942b48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688090(v=OCS.15)
ms:contentKeyID: 49733689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d60b3ba622e88978a8bbf555972c95979e8f8c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743753"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-remaining-users-to-lync-server-2013"></a>將剩餘使用者移到 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-29_

您可以使用 Lync Server [控制台] 或 [Lync Server 管理命令介面]，將使用者移至新的 Lync Server 2013 部署。 您必須符合一些需求，才能確保順利轉換至 Lync Server 2013。 如需有關完成本主題中程式的先決條件的詳細資訊，請參閱[設定要遷移的用戶端](configure-clients-for-migration.md)。 如需有關移動使用者的詳細步驟，請參閱[階段4：將測試使用者移至試驗池](phase-4-move-test-users-to-the-pilot-pool.md)。

<div>


> [!IMPORTANT]  
> 您無法使用 Active Directory 使用者和電腦管理單元或 Lync Server 2010 系統管理工具，將使用者從您的舊版環境移至 Lync Server 2013。



</div>

當您將使用者移至 Lync Server 2013 池時，使用者的資料會移至與新的資料庫池相關聯的後端資料庫。

<div>


> [!IMPORTANT]  
> 這包括舊版使用者建立的作用中會議。 例如，如果舊版使用者已設定「我的<STRONG>會議</STRONG>會議，則在使用者移動之後，新的 Lync Server 2013 池中仍會提供該會議。 存取該會議的詳細資料仍會是相同的<STRONG>會議 URL 與會議 ID</STRONG>。 唯一的差異在於，該會議現在已託管在 Lync Server 2013 池中，而不是在 Lync Server 2010 池中。



</div>

<div>


> [!NOTE]  
> 在 Lync Server 2013 上託管使用者並不需要您同時部署已升級的用戶端。 只有在使用者升級至新的用戶端軟體時，才能使用新的功能。



</div>

<div>

## <a name="post-migration-task"></a>遷移後任務

1.  在您移動使用者之後，請確認指派給他們的會議原則。

2.  若要確保由駐留在 Lync Server 2013 的使用者組織的會議能與駐留在 Lync Server 2010 的聯盟使用者順暢運作，指派給已遷移使用者的會議原則應該允許匿名參與者。

3.  允許匿名參與者的會議原則**允許參與者邀請**lync server 2013 [控制台] 中選取的匿名使用者，並在 Lync Server 管理命令介面的 [ **CsConferencingPolicy** ] Cmdlet 的輸出中，將**AllowAnonymousParticipantsInMeetings**設為**True** 。

4.  如需使用 Lync Server 管理命令介面設定會議原則的詳細資訊，請參閱 Lync Server 管理命令介面檔中的[設定 CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

