---
title: Lync Server 2013：為使用者設定電話語音
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97f4fc79b871a962fe498d6dbd908b75f6b2fecd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a>在 Lync Server 2013 中設定使用者的電話語音

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-11-01_

電話設定是使用者帳戶的一些個別設定，可在使用者的 Lync Server [控制台] 中設定（即，如果已啟用 Lync Server 2013 的個別使用者，且組織支援電話語音）。

Lync Server 使用者電話選項包括下列各項：

  - **音訊/視頻已停**   用使用者無法使用音訊和影片進行通話。

  - **僅電腦至電腦**   使用者只能進行 pc 對電腦音訊或視頻通話。

  - **企業語音**   使用者可以使用 Lync Server 2013 基礎結構來路由所有來電和撥出電話。 使用者也可以進行 PC 對電腦通話。

  - **[遠端通話控制**   ] 使用者可以使用 Lync Server 2013 來控制桌面電話，也可以進行 pc 對電腦通話。

如需設定組織的電話語音的詳細資料，請參閱在 [lync server 2013] 中[設定使用者的電話](lync-server-2013-configure-telephony-for-a-user.md)，以及在 [部署] 檔的 [ [lync server 2013] 中部署企業語音](lync-server-2013-deploying-enterprise-voice.md)。

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a>針對特定的使用者帳戶設定電話語音

1.  從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**使用者**]。

4.  在 [**搜尋使用者**] 方塊中，輸入您想要的 [顯示名稱]、[名字]、[姓氏]、[安全帳戶管理員] （SAM）帳戶名稱、SIP 位址或行統一資源識別項（URI）的全部或第一個部分，然後按一下 [**尋找**]。

5.  在表格中，按一下您要修改的使用者帳戶。

6.  按一下 [**編輯**] 功能表上的 [**修改**]。

7.  在 [**電話**] 中，執行下列動作：
    
      - 若要停用使用者的音訊和視頻通話，請按一下 [**音訊/視頻停用**]。
    
      - 若要為使用者啟用 PC 對電腦音訊通訊，但不啟用遠端通話控制或企業語音，請按一下 [**僅電腦至電腦**]。 針對使用者在 pc 對電腦音訊通訊所用的電話，指定**行 URI**的值。
    
      - 若要使用 Lync Server 2010 基礎結構根據服務策略類別（包括 PC 對電腦音訊通訊）來路由使用者的電話，請按一下 [**企業語音**]。 在 [**行 URI**] 中，指定企業語音的電話號碼。 在 [**撥號計畫原則**] 和 [**語音原則**] 中，為使用者指定適當的原則。 若要指定將使用者撥打的電話號碼轉換為 e. 164 格式的正常化規則，請在**位置原則**中選取適當的位置設定檔。
    
      - 若要啟用遠端通話控制，讓使用者能夠從 Lync Server 2013 控制其桌面電話線路，以進行 PC 對電腦通話和 PC 到電話的通話，請按一下 [**遠端通話控制**]。 在 [**行 URI**] 中，指定遠端通話控制的電話號碼。 使用者必須有桌面手機和私人分支 exchange （PBX）連線才能進行呼叫路由。

</div>

<div>

## <a name="see-also"></a>請參閱


[在 Lync Server 2013 中修改使用者帳戶屬性](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

