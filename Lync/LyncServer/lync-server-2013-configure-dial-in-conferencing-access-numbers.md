---
title: Lync Server 2013：設定電話撥入式會議存取號碼
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure dial-in conferencing access numbers
ms:assetid: d8a18030-f318-43dd-834d-70e5014b5e8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398952(v=OCS.15)
ms:contentKeyID: 48185623
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83c7069db95d36e79d74cea81faf3aa98685832f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504770"
---
# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>在 Lync Server 2013 中設定電話撥入式會議存取號碼

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2011-07-17_

當您部署電話撥入式會議時，您必須設定使用者可以從公用交換電話網路 (PSTN) 撥打的電話號碼，以加入會議的音訊部分。 這些撥入存取號碼會顯示在會議邀請和電話撥入式會議設定網頁上。

在您可以建立撥入存取號碼之前，您必須先規劃撥入式會議區域，然後使用地區設定撥號對應表。 如需地區的詳細資訊，請參閱規劃檔中的 [Lync Server 2013 中的電話撥入式會議需求](lync-server-2013-dial-in-conferencing-requirements.md) 。 如需設定電話撥入式會議的撥號對應表的詳細資訊，請參閱 [在 Lync Server 2013 中設定電話撥入式會議的撥號](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)對應表。

<div>


> [!NOTE]  
> 您無法使用新的撥入存取號碼，除非 Active Directory 網域服務 (AD &nbsp; DS) 該存取號碼的複寫已完成。 複寫可能需要數小時才能完成。



</div>

<div>


> [!NOTE]  
> 在您建立撥入存取號碼之後，您可以修改 Active Directory 連絡人物件的顯示名稱，讓使用者可以更輕鬆地識別正確的存取號碼。 使用 <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> Cmdlet 可修改顯示名稱。 您不應該手動修改 Active Directory 物件。 如需修改存取號碼的詳細資訊，請參閱 <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> Cmdlet 的 Lync Server 管理命令介面檔。



</div>

<div>

## <a name="in-this-section"></a>本章節內容

[在 Lync Server 2013 中建立或修改電話撥入式會議存取號碼](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a>另請參閱


[Lync Server 2013 中的電話撥入式會議需求](lync-server-2013-dial-in-conferencing-requirements.md)  


[在 Lync Server 2013 中設定電話撥入式會議的撥號對應表](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

