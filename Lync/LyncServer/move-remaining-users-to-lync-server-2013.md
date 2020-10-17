---
title: 將剩餘的使用者移至 Lync Server 2013
description: 將剩餘的使用者移至 Lync Server 2013。
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
ms.openlocfilehash: 291b58d6644f9ac8f10c63f6585ba865602580df
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571309"
---
# <a name="move-remaining-users-to-lync-server-2013"></a>將剩餘的使用者移至 Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-09-29_

您可以使用 Lync Server 控制台或 Lync Server 管理命令介面，將使用者移至新的 Lync Server 2013 部署。 您必須符合某些需求，以確保順利轉換至 Lync Server 2013。 如需完成本主題中程式之必要條件的詳細資訊，請參閱 [設定用戶端進行遷移](configure-clients-for-migration.md)。 如需移動使用者的詳細步驟，請參閱 [第4階段：將測試使用者移至試驗集](phase-4-move-test-users-to-the-pilot-pool.md)區。

<div>


> [!IMPORTANT]  
> 您無法使用 Active Directory 使用者及電腦嵌入式管理單元或 Lync Server 2010 系統管理工具，將使用者從舊版環境移至 Lync Server 2013。



</div>

當您將使用者移至 Lync Server 2013 集區時，使用者的資料會移至與新集區相關聯的後端資料庫。

<div>


> [!IMPORTANT]  
> 這包括由舊使用者所建立之作用中的會議。 例如，如果舊版使用者已設定「我的 <STRONG>會議</STRONG> 會議」，該會議在使用者移動之後仍會在新的 Lync Server 2013 集區中使用。 存取該會議的詳細資料仍為相同的 <STRONG>[會議 URL 及會議 ID]</STRONG>。 唯一的差別在於會議現在是主控于 Lync Server 2013 集區，而不是 Lync Server 2010 集區。



</div>

<div>


> [!NOTE]  
> 在 Lync Server 2013 上執行使用者，不需要同時部署已升級的用戶端。 只有當使用者已升級為新的用戶端軟體時，才可使用新功能。



</div>

<div>

## <a name="post-migration-task"></a>移轉後的工作

1.  一旦移除使用者之後，請驗證指派給他們的會議原則。

2.  為了確保以 Lync Server 2013 組織的使用者所組織的會議能夠與駐留在 Lync Server 2010 的同盟使用者順利運作，指派給已遷移使用者的會議原則應該允許匿名參與者。

3.  允許匿名參與者的會議原則**允許參與者邀請**lync Server 2013 控制台中所選取的匿名使用者，而且**AllowAnonymousParticipantsInMeetings**在 lync server 管理命令介面中從**Get-CsConferencingPolicy** Cmdlet 的輸出中，設定為**True** 。

4.  如需使用 Lync Server 管理命令介面設定會議原則的詳細資訊，請參閱 Lync Server 管理命令介面檔中的 [CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingPolicy) 。

</div>

</div>

<span> </span>

</div>

</div>

</div>

