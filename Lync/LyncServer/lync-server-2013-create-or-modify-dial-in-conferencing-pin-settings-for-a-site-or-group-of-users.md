---
title: Lync Server 2013：建立或修改使用者站台或群組的電話撥入式會議 PIN 設定
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
ms.openlocfilehash: 0ec453051e6ef9786e66a2b4d5f6dc4e48d6656f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a>在 Lync Server 2013 中建立或修改使用者站台或群組的電話撥入式會議 PIN 設定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-10-18_

請依照下列步驟來建立或修改使用者層級電話撥入式會議個人識別碼（PIN）原則。 如需如何變更全域 PIN 原則的詳細資料，請參閱[在 Lync Server 2013 中修改預設的電話撥入式會議 PIN 設定](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)。

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a>建立使用者或網站 PIN 原則

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**會議**]，然後按一下 [ **PIN 規則**]。

4.  在 [ **PIN 原則**] 頁面上，按一下 [**新增**]，然後執行下列其中一項操作：
    
      - 若要建立使用者層級原則，按一下 [**使用者原則**]。 在 [**新 PIN 原則**] 的 [**名稱**] 中，輸入描述原則的名稱。
    
      - 若要建立網站層級原則，按一下 [**網站原則**]。 在 [**選取網站**搜尋] 欄位中，輸入您要為其建立原則之網站的全部或部分名稱。 在網站清單中，按一下您想要的網站，然後按一下 **[確定]**。

5.  在 [**描述**] 欄位中，輸入 PIN 原則的描述。

6.  在 [**最小 pin 長度**] 欄位中，輸入或選取您要允許的最小 PIN 長度。 預設的最小長度為5位數。

7.  若要在封鎖使用者之前，能夠指定最大的登入嘗試次數，請選取 [**指定最大登入嘗試**] 核取方塊。 如果您沒有選取此選項，則會根據 PIN 長度自動判斷允許的最大嘗試次數上限。 根據預設，會自動決定最大嘗試次數。

8.  如果您已選取 [**指定最大登入嘗試**] 核取方塊，請在 [**最大登入次數**] 中，輸入或選取您要允許的最大登入嘗試次數。

9.  若要讓 Pin 到期，請選取 [**啟用 PIN 到期**日] 核取方塊。 如果您沒有選取此選項，針腳將永不過期。 根據預設，Pin 永遠不會過期。

10. 如果您已選取 [**啟用 PIN 到期**日] 核取方塊，請在 **[PIN 到期日之後（天數）**] 中，輸入或選取 pin 到期前的天數。

11. 在 [ **PIN 記錄計數**] 中，輸入使用者必須建立才能重複使用 pin 的 pin 數。 根據預設，使用者可以重複使用他們的 Pin。

12. 若要在 Pin 中允許通用位數（例如順序編號和重複的數位組），請選取 [**允許常見模式**] 核取方塊。 如果您沒有選取此選項，則只允許使用複雜的數位模式。 根據預設，只允許使用複雜的數位模式。
    
    <div>
    

    > [!IMPORTANT]
    > 我們建議您不要允許通用模式。

    
    </div>

13. 按一下 [認可]****。

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a>變更使用者或網站的 PIN 原則

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**會議**]，然後按一下 [ **PIN 規則**]。

4.  在 [ **PIN 原則**] 頁面上，按一下您要變更的固定原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**編輯 PIN 原則**] 中，修改任何原則設定（除了不能修改的原則名稱之外）。

6.  按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

