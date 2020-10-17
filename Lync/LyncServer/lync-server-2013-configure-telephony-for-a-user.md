---
title: Lync Server 2013：設定使用者的電話語音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 86eade8f7a2ac1db627668ca78b8fb7869e6da71
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520370"
---
# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>在 Lync Server 2013 中設定使用者的電話語音

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

電話語音設定是使用者帳戶的一些個別設定，可在 Lync Server 控制台中針對使用者 (設定，也就是說，如果個別使用者已啟用 Lync Server 2013，而組織支援電話語音) 。

Lync Server 使用者電話語音選項包括下列各項：

  - **已停用**     音訊/視頻使用者無法使用音訊和影片進行通話。

  - **僅限**     電腦對電腦使用者只能進行電腦對電腦音訊或視頻通話。

  - **Enterprise Voice**    使用者可以使用 Lync Server 2013 基礎結構路由傳送所有來電和撥出電話。 使用者也可以進行電腦對電腦呼叫。

  - **遠端呼叫控制**    使用者可以使用 Lync Server 2013 來控制電腦電話，也可以進行電腦對電腦通話。

如需設定組織之電話語音的詳細資訊，請參閱部署檔中的在 lync Server [2013 中設定使用者的電話語音](lync-server-2013-configure-telephony-for-a-user.md) ，以及在 [lync Server 2013 中部署 Enterprise Voice](lync-server-2013-deploying-enterprise-voice.md) 。

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>若要設定特定使用者帳戶的電話語音

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶，登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱 [Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 **[使用者]**。

4.  在 **[搜尋使用者]** 方塊中，輸入您要的使用者帳戶的完整或開頭部分的顯示名稱、名字、姓氏、安全性帳戶管理員 (SAM) 帳戶名稱、SIP 位址或線路統一資源識別項 (URI)，然後按一下 **[尋找]**。

5.  在表格中，按一下您要修改的使用者帳戶。

6.  在 **[編輯]** 功能表中，按一下 **[修改]**。

7.  在 **[電話語音]** 中，執行下列動作：
    
      - 若要停用使用者的音訊和視訊電話，請按一下 **[音訊/視訊已停用]**。
    
      - 若要啟用使用者的電腦對電腦音訊通訊，但不啟用遠端呼叫控制或 Enterprise Voice，請按一下 **[僅限電腦對電腦]**。針對使用者用於電腦對電腦音訊通訊的電話，指定 **[線路 URI]** 值。
    
      - 若要依照服務原則類別（包括 PC 對電腦音訊通訊）使用 Lync Server 2010 基礎結構來路由傳送使用者的電話，請按一下 [ **Enterprise Voice**]。 在 **[線路 URI]** 中，指定 Enterprise Voice 的電話號碼。 在 **[撥號對應表原則]** 和 **[語音原則]** 中，指定使用者的適當原則。 若要指定將使用者撥打的電話號碼轉譯為 E.164 格式時的正規化規則，請在 **[位置原則]** 中選取適當的位置設定檔。
    
      - 若要啟用遠端呼叫控制，可讓使用者從 Lync Server 2013 控制其桌面電話線路，以進行 PC 對電腦通話和 PC 對電話的呼叫，請按一下 [ **遠端呼叫控制**]。 在 **[線路 URI]** 中，指定遠端呼叫控制的電話號碼。 使用者必須有桌上電話和用於電話路由的專用交換機 (PBX) 連線。

</div>

<div>

## <a name="see-also"></a>另請參閱


[在 Lync Server 2013 中修改使用者帳戶屬性](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

