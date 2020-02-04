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
ms.openlocfilehash: e19d594b8d1661a314b834e6c2e92d8668490ad7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757907"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>在 Lync Server 2013 中設定電話撥入式會議存取號碼

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2011-07-17_

當您部署電話撥入式會議時，您必須設定使用者可從公用交換電話網絡（PSTN）撥打電話的電話號碼，以加入會議的音訊部分。 這些撥入存取號碼會出現在會議邀請和 [電話撥入式會議設定] 網頁上。

您必須先規劃撥入式會議區域，然後設定與地區的撥號方案，才能建立撥入號碼。 如需地區的詳細資訊，請參閱規劃檔中的[Lync Server 2013 中的電話撥入式會議需求](lync-server-2013-dial-in-conferencing-requirements.md)。 如需有關設定電話撥入式會議的撥號方案的詳細資訊，請參閱[在 Lync Server 2013 中設定電話撥入式會議的撥號方案](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)。

<div>


> [!NOTE]  
> 在該存取號碼的 Active Directory 網域服務（AD&nbsp;DS）複製完成之前，您無法使用新的撥入存取號碼。 複製可能需要幾個小時才能完成。



</div>

<div>


> [!NOTE]  
> 在您建立撥入存取號碼之後，您可以修改 Active Directory 連絡人物件的顯示名稱，讓使用者能更輕鬆地識別正確的存取號碼。 使用<STRONG>CsDialInConferencingAccessNumber</STRONG> Cmdlet 來修改顯示名稱。 您不應該手動修改 Active Directory 物件。 如需有關修改存取號碼的詳細資訊，請參閱<STRONG>CsDialInConferencingAccessNumber</STRONG> Cmdlet 的 Lync Server Management 命令介面檔。



</div>

<div>

## <a name="in-this-section"></a>本節內容

[在 Lync Server 2013 中建立或修改電話撥入式會議存取號碼](lync-server-2013-create-or-modify-a-dial-in-conferencing-access-number.md)

</div>

<div>

## <a name="see-also"></a>請參閱


[Lync Server 2013 中的電話撥入式會議需求](lync-server-2013-dial-in-conferencing-requirements.md)  


[在 Lync Server 2013 中設定電話撥入式會議的撥號對應表](lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

