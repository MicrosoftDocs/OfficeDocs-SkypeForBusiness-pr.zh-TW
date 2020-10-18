---
title: Lync Server 2013： (選用) 驗證電話撥入式會議
description: Lync Server 2013： (選用) 驗證電話撥入式會議。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify dial-in conferencing
ms:assetid: 3e2b4220-8fb3-442f-98b1-78447adb321f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425905(v=OCS.15)
ms:contentKeyID: 48183941
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5e8d3734e89555bf4b298ac68e1e3bd67b1d901
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572532"
---
# <a name="optional-verify-dial-in-conferencing-in-lync-server-2013"></a> (選用) 驗證 Lync Server 2013 中的電話撥入式會議

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主題上次修改日期：** 2011-01-21_

若要確認電話撥入式會議設定網頁和撥入式存取號碼正確運作，您需要執行下列動作：

  - 登入簡單 URL，以測試 [電話撥入式會議設定] 網頁。

  - 執行本主題稍後的指令碼，以測試特定集區的存取號碼是否正常運作。此指令碼會模擬撥打存取號碼。您需要特定集區裝載控之某個整合通訊 (UC) 用戶端的 SIP 位址和認證，才能使用此指令碼。

這是選用步驟。

<div>

## <a name="to-test-access-numbers-for-a-specific-pool"></a>若要測試特定集區的存取號碼

1.  以 RTCUniversalServerAdmins 群組成員或 **Cs-ServerAdministrator**、**CsAdministrator** 角色成員的身分登入電腦。

2.  啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。

3.  在命令提示字元中執行下列命令：
    
        $credentials = Get-Credential
           User name:  testuser1@contoso.com
           Password:   ********
        Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose
    
    產生的報告會顯示「成功」或「失敗」，以及特定的診斷資訊。使用 -Verbose 旗標會進一步顯示找到幾個存取號碼，以及這些存取號碼的詳細資料。

</div>

</div>

<span> </span>

</div>

</div>

</div>

