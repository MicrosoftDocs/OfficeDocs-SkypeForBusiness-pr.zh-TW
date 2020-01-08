---
title: Lync Server 2013：(選用) 驗證電話撥入式會議
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70a0b18ce596e4799c82a2843b5f3a008b5cb285
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013 中的 (選用) 驗證電話撥入式會議

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2011-01-21_

若要確認電話撥入式會議設定網頁和撥入式存取號碼都能正常運作，您必須執行下列動作：

  - 登入簡單的 URL，測試電話撥入式會議設定網頁。

  - 您可以在本主題稍後執行腳本，以測試存取號碼是否能在特定的池中正常運作。 此腳本會類比存取號碼的通話。 您需要在特定的池中託管的單一整合通訊（UC）用戶端的 SIP 位址和認證，才能使用此腳本。

此為選用步驟。

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a>測試特定資源的存取號碼

1.  以 RTCUniversalServerAdmins 群組的成員或**Cs-ServerAdministrator**或**CsAdministrator**角色的成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元執行下列動作：
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    產生的報告會顯示成功或失敗，以及特定的診斷資訊。 -Verbose 標誌提供有關已找到多少個存取號碼的詳細資訊，以及它們的詳細資料。

</div>

</div>

<span> </span>

</div>

</div>

</div>

