---
title: Lync Server 2013：建立或修改網站或使用者群組的電話撥入式會議 PIN 設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify dial-in conferencing PIN settings for a site or group of users
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48185326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b3a1ea4ed8643daaecd2ef15b9cffb0c7b65bab
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a>為網站或使用者群組建立或修改 Lync Server 2013 中的電話撥入式會議 PIN 設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

請遵循下列步驟，建立或修改使用者層級或網站層級的撥入式會議個人身分識別號碼 (PIN) 原則。 如需如何變更全域 PIN 原則的詳細資訊，請參閱[在 Lync Server 2013 中修改預設電話撥入式會議 PIN 設定](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)。

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a>建立使用者或網站 PIN 原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [會議]**** 再按一下 [PIN 原則]****。

4.  在 [ **PIN 原則**] 頁面上，按一下 [**新增**]，然後執行下列其中一項動作：
    
      - 若要建立使用者層級原則，請按一下 [**使用者原則**]。 在 [**新增 PIN 原則**] 的 [**名稱**] 中，輸入描述原則的名稱。
    
      - 若要建立網站層級原則，請按一下 [**網站原則**]。 在 [**選取網站**] 搜尋欄位中，輸入您要建立原則的網站名稱全部或部分名稱。 在網站清單中，按一下您想要的網站，然後按一下 **[確定]**。

5.  在 [**描述**] 欄位中，輸入 PIN 原則的描述。

6.  在 [**最小 PIN 碼長度**] 欄位中，輸入或選取您想要允許的最小 pin 碼長度。 預設的最小長度為五位數。

7.  若要能夠指定使用者遭鎖定前可嘗試登入的次數上限，請選取 **[指定登入嘗試次數上限]** 核取方塊。若未選取此選項，則會根據 PIN 長度自動指定允許的嘗試次數上限。依預設會自動指定嘗試次數上限。

8.  如果您選取了 **[指定登入嘗試次數上限]** 核取方塊，請在 **[登入嘗試次數上限]** 中輸入或選取您所要允許的登入嘗試次數上限。

9.  若要讓 PIN 有期限，請選取 **[啟用 PIN 到期]** 核取方塊。若未選取此選項，PIN 將永不過期。根據預設，PIN 永遠不會過期。

10. 如果您選取了 **[啟用 PIN 到期]** 核取方塊，請在 **[PIN 於下列日數後到期]** 中輸入或選取 PIN 將在幾天之後到期。

11. 在 **[PIN 碼歷程記錄計數]** 中，輸入使用者必須在建立多少個 PIN 之後才可重複使用 PIN。根據預設，使用者可重複使用其 PIN。

12. 若要允許在 PIN 中使用共同模式的數字 (如連續數字與重複數字組)，請選取 **[允許共同模式]** 核取方塊。若未選取此選項，則只會允許複合模式的數字。依預設只會允許複合模式的數字。
    
    <div>
    

    > [!IMPORTANT]
    > 建議您不要允許共同模式。

    
    </div>

13. 按一下 **[認可]**。

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a>變更使用者或網站 PIN 原則

1.  從 RTCUniversalServerAdmins 群組成員的使用者帳戶 (或擁有同等的使用者權限) 或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您已部署 Lync Server 2013 之網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入管理 URL 以開啟 Lync Server 控制台。 如需您可以用來啟動 Lync Server 控制台之不同方法的詳細資訊，請參閱[Open Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左導覽列中，按一下 [會議]**** 再按一下 [PIN 原則]****。

4.  在 [ **PIN 原則**] 頁面上，按一下您要變更的 PIN 原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**編輯 PIN 原則**] 中，修改原則名稱 (以外的任何原則設定，但無法修改) 。

6.  按一下 **[認可]**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

