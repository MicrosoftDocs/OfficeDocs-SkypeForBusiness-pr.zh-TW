---
title: Lync Server 2013： 設定自訂目前狀態
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring custom presence states
ms:assetid: e17364a8-8b93-45fc-a614-c80e45435d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398997(v=OCS.15)
ms:contentKeyID: 48185534
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f93229ee06a3d45db2478003a18ac22a2e7cf59
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42203099"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-custom-presence-states-in-lync-server-2013"></a><span data-ttu-id="460e4-102">在 Lync Server 2013 中設定自訂目前狀態</span><span class="sxs-lookup"><span data-stu-id="460e4-102">Configuring custom presence states in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="460e4-103">_**上次修改主題：** 2013年-01-10_</span><span class="sxs-lookup"><span data-stu-id="460e4-103">_**Topic Last Modified:** 2013-01-10_</span></span>

<span data-ttu-id="460e4-104">若要在 Lync 2013 中定義自訂目前狀態，建立 XML 自訂目前狀態設定檔，並接著藉由使用 Lync Server 管理命令介面 cmdlet **New-csclientpolicy**或**Set-csclientpolicy**搭配參數 customstateurl 來指定其位置。</span><span class="sxs-lookup"><span data-stu-id="460e4-104">To define custom presence states in Lync 2013, create an XML custom presence configuration file, and then specify its location by using the Lync Server Management Shell cmdlets **New-CSClientPolicy** or **Set-CSClientPolicy** with the parameter CustomStateURL.</span></span>

<span data-ttu-id="460e4-105">設定檔包含下列屬性：</span><span class="sxs-lookup"><span data-stu-id="460e4-105">Configuration files have the following properties:</span></span>

  - <span data-ttu-id="460e4-106">可以使用適用於 」、 「 忙碌 」 和 「 請勿打擾顯示狀態指示器來設定自訂目前狀態。</span><span class="sxs-lookup"><span data-stu-id="460e4-106">Custom presence states can be configured with the Available, Busy, and Do Not Disturb presence indicators.</span></span>

  - <span data-ttu-id="460e4-107">可用性屬性會決定關聯的自訂狀態的狀態文字的顯示狀態指示器。</span><span class="sxs-lookup"><span data-stu-id="460e4-107">The availability attribute determines which presence indicator is associated with the status text of the custom state.</span></span> <span data-ttu-id="460e4-108">在本主題稍後的範例中，狀態文字在家工作會顯示綠色 （線上） 顯示狀態指示器的右邊。</span><span class="sxs-lookup"><span data-stu-id="460e4-108">In the example later in this topic, the status text Working from Home is displayed to the right of the green (Available) presence indicator.</span></span>

  - <span data-ttu-id="460e4-109">狀態文字的長度上限是 64 個字元。</span><span class="sxs-lookup"><span data-stu-id="460e4-109">The maximum length of the status text is 64 characters.</span></span>

  - <span data-ttu-id="460e4-110">可以新增最多四個自訂目前狀態。</span><span class="sxs-lookup"><span data-stu-id="460e4-110">A maximum of four custom presence states can be added.</span></span>

  - <span data-ttu-id="460e4-111">CustomStateURL 參數指定的組態檔的位置。</span><span class="sxs-lookup"><span data-stu-id="460e4-111">The CustomStateURL parameter specifies the location of the configuration file.</span></span> <span data-ttu-id="460e4-112">在 Lync 2013 中，SIP 高安全性模式預設會啟用，因此您需要儲存網頁伺服器已啟用 HTTPS 上的自訂目前狀態設定檔。</span><span class="sxs-lookup"><span data-stu-id="460e4-112">In Lync 2013, SIP high security mode is enabled by default, so you will need to store the custom presence configuration file on a web server that has HTTPS enabled.</span></span> <span data-ttu-id="460e4-113">否則，Lync 2013 用戶端將無法連線到它。</span><span class="sxs-lookup"><span data-stu-id="460e4-113">Otherwise, Lync 2013 clients will be unable to connect to it.</span></span> <span data-ttu-id="460e4-114">例如，就是有效的地址`https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`。</span><span class="sxs-lookup"><span data-stu-id="460e4-114">For example, a valid address would be `https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml`.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="460e4-115">雖然不建議在生產環境中，您可以測試的組態檔，位於非 HTTPS 檔案共用上使用 EnableSIPHighSecurityMode 登錄設定，停用用戶端上的 SIP 高安全性模式。</span><span class="sxs-lookup"><span data-stu-id="460e4-115">Although it is not recommended in a production environment, you can test a configuration file that is located on a non-HTTPS file share by using the EnableSIPHighSecurityMode registry setting to disable SIP high security mode on the client.</span></span> <span data-ttu-id="460e4-116">然後您可以使用 customstateurl 來登錄設定來指定的組態檔的非 HTTPS 位置。</span><span class="sxs-lookup"><span data-stu-id="460e4-116">Then you can use the CustomStateURL registry setting to specify a non-HTTPS location for the configuration file.</span></span> <span data-ttu-id="460e4-117">請注意，Lync 2013 接受 Lync 2010 登錄設定，但已更新登錄區。</span><span class="sxs-lookup"><span data-stu-id="460e4-117">Note that Lync 2013 honors Lync 2010 registry settings, but the registry hive has been updated.</span></span> <span data-ttu-id="460e4-118">您可以建立的登錄設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="460e4-118">You would create the registry settings as follows:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="460e4-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span><span class="sxs-lookup"><span data-stu-id="460e4-119">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\EnableSIPHighSecurityMode</span></span></P>
> <P><span data-ttu-id="460e4-120">類型： DWORD</span><span class="sxs-lookup"><span data-stu-id="460e4-120">Type: DWORD</span></span></P>
> <P><span data-ttu-id="460e4-121">數值資料： 0</span><span class="sxs-lookup"><span data-stu-id="460e4-121">Value data: 0</span></span></P>
> <LI>
> <P><span data-ttu-id="460e4-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span><span class="sxs-lookup"><span data-stu-id="460e4-122">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync\CustomStateURL</span></span></P>
> <P><span data-ttu-id="460e4-123">類型： 字串 (REG_SZ)</span><span class="sxs-lookup"><span data-stu-id="460e4-123">Type: String (REG_SZ)</span></span></P>
> <P><span data-ttu-id="460e4-124">數值資料 （範例）： file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml 或 file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span><span class="sxs-lookup"><span data-stu-id="460e4-124">Value data (examples): file://\\lspool.corp.contoso.com\LSFileShare\ClientConfigFolder\Presence.xml or file:///c:/LSFileShare/ClientConfigFolder/Group_1_Pres.xml</span></span></P></LI></UL>



</div>

<span data-ttu-id="460e4-125">XML 設定檔，以指定一或多個地區設定識別碼 (LCID) 結構描述當地語系化您自訂目前狀態。</span><span class="sxs-lookup"><span data-stu-id="460e4-125">Localize your custom presence state by specifying one or more locale ID (LCID) schema in the XML configuration file.</span></span> <span data-ttu-id="460e4-126">稍後在這個範例主題會顯示成英文-當地語系化 United States (1033)、 挪威文-巴克摩 (1044)、 法文-法國 (1036) 及土耳其文 (1055)。</span><span class="sxs-lookup"><span data-stu-id="460e4-126">The example later in this topic shows localization into English - United States (1033), Norwegian - Bokmål (1044), French - France (1036), and Turkish (1055).</span></span> <span data-ttu-id="460e4-127">Lcid 的清單，請參閱在 microsoft 指派的地區識別碼<https://go.microsoft.com/fwlink/p/?linkid=157331>。</span><span class="sxs-lookup"><span data-stu-id="460e4-127">For a list of LCIDs, see Locale IDs Assigned by Microsoft at <https://go.microsoft.com/fwlink/p/?linkid=157331>.</span></span>

<div>

## <a name="to-add-custom-presence-states-to-lync-2013"></a><span data-ttu-id="460e4-128">若要將自訂目前狀態新增至 Lync 2013</span><span class="sxs-lookup"><span data-stu-id="460e4-128">To add custom presence states to Lync 2013</span></span>

1.  <span data-ttu-id="460e4-129">建立使用下列範例格式的 XML 設定檔：</span><span class="sxs-lookup"><span data-stu-id="460e4-129">Create an XML configuration file that uses the format of the following example:</span></span>
    
        <?xml version="1.0"?>
        <customStates xmlns="http://schemas.microsoft.com/09/2009/communicator/customStates">
          <customState ID="1" availability="online">
            <activity LCID="1033">Working from Home</activity>
            <activity LCID="1044">activity 2 for 1044</activity>
            <activity LCID="1055">activity 3 for 1055</activity>
          </customState>
          <customState ID="2" availability="busy">
            <activity LCID="1033">In a Live Meeting</activity>
            <activity LCID="1036">Equivalent French String for - In a Live Meeting </activity>
          </customState>
          <customState ID="3" availability="busy">
            <activity LCID="1033">Meeting with Customer</activity>
            <activity LCID="1055">meeting with client</activity>
            <activity LCID="1036">Equivalent French String for - Meeting with Customer</activity>
          </customState>
          <customState ID="4" availability="do-not-disturb">
            <activity LCID="1033">Interviewing</activity>
          </customState>
        </customStates>

2.  <span data-ttu-id="460e4-130">儲存至網頁伺服器的 XML 設定檔，以啟用 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="460e4-130">Save the XML configuration file to a web server with HTTPS enabled.</span></span> <span data-ttu-id="460e4-131">在這個範例中，該檔案是名為 Presence.xml 和儲存位置， https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml。</span><span class="sxs-lookup"><span data-stu-id="460e4-131">In this example, the file is named Presence.xml and saved to the location https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml.</span></span>

3.  <span data-ttu-id="460e4-132">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="460e4-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="460e4-133">在 Lync Server 管理命令介面，定義在 XML 設定檔的位置使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="460e4-133">In the Lync Server Management Shell, define the location of your XML configuration file by using a command similar to the following:</span></span>
    
        New-CsClientPolicy -Identity ContosoCustomStates 
        -CustomStateURL "https://lspool.corp.contoso.com/ClientConfigFolder/CustomPresence.xml"

5.  <span data-ttu-id="460e4-134">使用**Grant-csclientpolicy** cmdlet 將此新原則指派給使用者。</span><span class="sxs-lookup"><span data-stu-id="460e4-134">Use the **Grant-CSClientPolicy** cmdlet to assign this new policy to users.</span></span>

<span data-ttu-id="460e4-135">如需詳細資訊，請參閱 Lync Server 管理命令介面文件中的[New-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy)和[Grant-csclientpolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) 。</span><span class="sxs-lookup"><span data-stu-id="460e4-135">For details, see [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) and [Grant-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsClientPolicy) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P><span data-ttu-id="460e4-136">根據預設，Lync Server 2013&nbsp;每三小時更新用戶端原則和設定。</span><span class="sxs-lookup"><span data-stu-id="460e4-136">By default, Lync Server 2013&nbsp;updates client policies and settings every three hours.</span></span></P>
> <LI>
> <P><span data-ttu-id="460e4-137">如果您想要繼續使用群組原則設定，從先前的版本，例如 CustomStateURL、 Lync 2013 會辨識設定，如果他們位於中新的原則登錄區 (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync)。</span><span class="sxs-lookup"><span data-stu-id="460e4-137">If you want to continue using Group Policy settings from previous releases, such as CustomStateURL, Lync 2013 will recognize the settings if they are located in the new policy registry hive (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Office\15.0\Lync).</span></span> <span data-ttu-id="460e4-138">不過，伺服器為基礎的用戶端原則的優先順序。</span><span class="sxs-lookup"><span data-stu-id="460e4-138">However, server-based client policies take precedence.</span></span></P></LI></UL>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

