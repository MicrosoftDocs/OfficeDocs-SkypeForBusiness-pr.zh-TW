---
title: Lync Server 2013：設定電話撥入式會議的會議原則
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
ms.openlocfilehash: 107c5fcf4b341c652cd4044fe47f4b650cf5adb4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a>在 Lync Server 2013 中設定電話撥入式會議的會議原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2014-03-21_

[會議原則] 是一個使用者帳戶設定，可為參與者指定會議體驗。 您可以使用網站範圍或使用者範圍建立會議原則。 會議原則設定涵蓋了會議排程與參與的許多方面。 幾個會議原則設定支援參與者的電話撥入式會議。 當您設定電話撥入式會議時，應確認這些欄位已針對您的組織進行適當的設定，並視需要加以修改。

驗證會議原則中的下欄欄位：

  - **[允許參與者邀請匿名使用者**   ] 此設定可讓會議召集人邀請匿名（也就是未驗證）參與者加入會議。 此設定為電話撥入式會議的選用。 預設的全域會議原則預設會選取此設定。

  - **啟用 PSTN 電話撥入式會議**   此設定可讓使用者透過撥入 PSTN 來加入會議的音訊部分。 電話撥入式會議需要此設定。 預設的全域會議原則預設會選取此設定。

  - **[允許匿名參與者撥號**   ] 此設定可讓已加入會議的匿名使用者撥出電話號碼，以加入會議的音訊部分。 此設定為電話撥入式會議的選用。 預設的全域會議原則預設不會選取此設定。

  - **[允許未啟用企業語音的參與者撥號**   ] 此設定可讓未啟用企業語音的會議參與者和召集人撥出電話號碼以加入會議的音訊部分。 撥出通話是根據召集人指派的語音原則進行授權。 預設的全域會議原則預設不會選取此設定。 [設定預設值] 為 [停用]。
    
    <div>
    

    > [!NOTE]  
    > 若要啟用這項功能，沒有為企業語音啟用的會議召集人應該已指派適當的語音原則，以授權來自該使用者組織之會議的任何撥出。 您可以從 Lync Server 管理命令介面將語音原則指派給未啟用企業語音的使用者。 如果使用者沒有明確指派給他的語音原則，網站語音原則將用來授權撥出要求。 如果沒有網站語音原則，就會使用全域語音原則。&nbsp;

    
    </div>

本節中的程式說明如何修改會議原則。 如需有關如何設定在預設會議原則中定義參與者體驗的所有設定的詳細資訊，請參閱[在 Lync Server 2013 中建立或修改會議配置設定的集合](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)。 如需如何為特定使用者或使用者群組建立會議原則的詳細資料，請參閱[在 Lync Server 2013 中建立或修改會議原則](lync-server-2013-create-or-modify-a-conferencing-policy.md)。 如需所有可用會議原則設定的清單，請參閱[Lync Server 2013 的會議原則設定參考](lync-server-2013-conferencing-policy-settings-reference.md)。

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a>修改電話撥入式會議原則

1.  以 RTCUniversalServerAdmins 群組的成員或**Cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**會議**]。

4.  在 [**會議原則**] 索引標籤上，按兩下會議原則名稱，以開啟 [**編輯會議原則**] 對話方塊。

5.  確認電話撥入式會議的欄位適合您的組織，並視需要修改設定。

6.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

