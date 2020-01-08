---
title: Lync Server 2013：修改現有的 PIN 原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify an existing PIN policy
ms:assetid: 517caaee-3349-4fa6-8d86-e4da3258a445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520993(v=OCS.15)
ms:contentKeyID: 48184143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16f763ebf0d1a8b74a8370ba7b4ca4913886c612
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977850"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-an-existing-pin-policy-in-lync-server-2013"></a>在 Lync Server 2013 中修改現有的 PIN 原則

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2012-06-19_

您可以使用 [**釘選原則**] 索引標籤，為使用 IP 電話連線至 Lync 2013 的使用者提供個人識別碼（pin）驗證。 若要使用 PIN 驗證，請確認已在 [Web 服務設定] 中選取 [**啟用 Pin 驗證**]。 如需詳細資訊，請參閱[在 Lync Server 2013 中修改現有的 Web 服務配置設定](lync-server-2013-modify-existing-web-service-configuration-settings.md)。

請依照這些步驟來修改使用者層級或網站層級的 PIN 原則。

<div>

## <a name="to-modify-an-existing-pin-policy"></a>修改現有的 PIN 原則

1.  從是 RTCUniversalServerAdmins 群組成員的使用者帳戶（或是擁有同等的使用者權利），或指派給 CsServerAdministrator 或 CsAdministrator 角色，登入您在其中部署 Lync Server 2013 的網路中的任何電腦。

2.  開啟瀏覽器視窗，然後輸入系統管理員 URL，以開啟 Lync Server [控制台]。 如需可用於啟動 Lync Server [控制台] 的不同方法的詳細資訊，請參閱[開啟 Lync server 2013 系統管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左側導覽列中，按一下 [**安全性**]，然後按一下 [ **PIN 規則**]。

4.  在 [ **PIN 原則**] 頁面上，按一下原則，按一下 [**編輯**]，然後按一下 [**顯示詳細資料**]。

5.  在 [**編輯 Pin 原則**] 的 [**最小 pin 長度**] 中，輸入或選取您要允許的最小 pin 長度。 預設的最小長度為5位數。

6.  若要在封鎖使用者之前，能夠指定最大的登入嘗試次數，請選取 [**指定最大登入嘗試**] 核取方塊。 如果您沒有選取此選項，則會根據 PIN 長度自動判斷允許的最大嘗試次數上限。 根據預設，會自動決定最大嘗試次數。

7.  如果您已選取 [**指定最大登入嘗試**] 核取方塊，請在 [**最大登入次數**] 中，輸入或選取您要允許的最大登入嘗試次數。

8.  若要讓 Pin 到期，請選取 [**啟用 PIN 到期**日] 核取方塊。 如果您沒有選取此選項，針腳將永不過期。 根據預設，Pin 永遠不會過期。

9.  如果您已選取 [**啟用 PIN 到期**日] 核取方塊，請在 **[PIN 到期日之後（天數）**] 中，輸入或選取 pin 到期前的天數。

10. 在 [ **PIN 記錄計數**] 中，輸入使用者必須建立才能重複使用 pin 的 pin 數。 根據預設，使用者可以重複使用他們的 Pin。

11. 若要在 Pin 中允許通用位數（例如順序編號和重複的數位組），請選取 [**允許常見模式**] 核取方塊。 如果您沒有選取此選項，則只允許使用複雜的數位模式。 根據預設，只允許使用複雜的數位模式。
    
    <div>
    

    > [!IMPORTANT]  
    > 我們建議您不要允許通用模式。

    
    </div>

12. 按一下 [認可]****。

</div>

</div>

<span> </span>

</div>

</div>

</div>

