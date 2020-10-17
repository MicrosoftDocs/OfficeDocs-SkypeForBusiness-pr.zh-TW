---
title: Lync Server 2013：設定電話撥入式會議原則
description: Lync Server 2013：設定電話撥入式會議原則。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd8dee1d9e7e6391c6420b15a895199dfc7a8791
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564389"
---
# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>在 Lync Server 2013 中設定電話撥入式會議原則

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-21_

會議原則是一種使用者帳戶設定，可指定參與者的會議體驗。 您可以建立具有網站範圍或使用者範圍的會議原則。 會議原則設定涵蓋許多會議排程和參與的層面。 數個會議原則設定支援參與者的電話撥入式會議。 當您設定電話撥入式會議時，應確認您的組織已正確設定這些欄位，並視需要加以修改。

驗證會議原則中的下欄欄位：

  - **允許參與者邀請匿名使用者**    此設定可讓會議召集人邀請匿名 (，也就是未驗證的) 參與者參加會議。 此設定為電話撥入式會議的選用。 預設會選取預設全域會議原則中的此設定。

  - **啟用 PSTN 電話撥入式會議**    此設定可讓使用者從 PSTN 撥入，以加入會議的音訊部分。 電話撥入式會議需要此設定。 預設會選取預設全域會議原則中的此設定。

  - **允許匿名參與者撥出**    此設定允許已經加入會議的匿名使用者撥出到電話號碼，以加入會議的音訊部分。 此設定為電話撥入式會議的選用。 預設全域會議原則中不會選取此設定。

  - **允許未啟用 Enterprise Voice 的參與者撥出**    此設定允許未啟用 Enterprise Voice 的會議參與者和召集人撥打至電話號碼，以加入會議的音訊部分。 撥出電話是根據召集人指派的語音原則獲得授權。 預設全域會議原則中不會選取此設定。 設定預設值為停用。
    
    <div>
    

    > [!NOTE]  
    > 若要啟用此功能，未啟用 Enterprise Voice 的會議召集人應該會有適當的語音原則指派給他們，以授權來自該使用者組織之會議的任何撥出。 語音原則可以指派給沒有從 Lync Server 管理命令介面中為 Enterprise Voice 啟用的使用者。 若使用者沒有明確指派給他的語音原則，則會使用網站語音原則來授權撥出要求。 如果沒有網站語音原則，則會使用通用語音原則。&nbsp;

    
    </div>

本節中的程式說明如何修改會議原則。 如需如何設定所有設定以定義預設會議原則中的參與者經驗的詳細資訊，請參閱在 [Lync Server 2013 中建立或修改會議配置設定的集合](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)。 如需如何為特定使用者或使用者群組建立會議原則的詳細資訊，請參閱 [建立或修改 Lync Server 2013 中的會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)。 如需所有可用之會議原則設定的清單，請參閱 [Lync Server 2013 的會議原則設定參考](lync-server-2013-conferencing-policy-settings-reference.md)。

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>若要修改電話撥入式會議原則

1.  以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 **[會議]**。

4.  在 [ **會議原則** ] 索引標籤上，按兩下會議原則名稱，以開啟 [ **編輯會議原則** ] 對話方塊。

5.  確認電話撥入式會議的欄位適用于您的組織，必要時會修改設定。

6.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

