---
title: 直接路由 - 連接類比裝置
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 請閱讀本文，瞭解如何在系統直接路由Microsoft 電話使用類比裝置。
ms.openlocfilehash: dc49c22dceffda6905d1f57652fd14d584d02cf6
ms.sourcegitcommit: 9d446485aa842abbdcd34d946b247166c2bf1610
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/25/2021
ms.locfileid: "52642093"
---
# <a name="how-to-use-analog-devices-with-phone-system-direct-routing"></a><span data-ttu-id="c974d-103">如何使用類比裝置電話系統直接路由</span><span class="sxs-lookup"><span data-stu-id="c974d-103">How to use analog devices with Phone System Direct Routing</span></span>

<span data-ttu-id="c974d-104">本文將說明如何將類比裝置與直接路由電話系統使用。</span><span class="sxs-lookup"><span data-stu-id="c974d-104">This article describes how to use analog devices with Phone System Direct Routing.</span></span> <span data-ttu-id="c974d-105">若要將類比裝置連接到直接路由，您必須使用類比電話轉接器 (ATA) ，且此配接器必須受到認證會話邊界控制器 (SBC) 廠商的支援。</span><span class="sxs-lookup"><span data-stu-id="c974d-105">To connect analog devices to Direct Routing, you must use an Analog Telephony Adapter (ATA), and this adapter must be supported by the certified Session Border Controller (SBC) vendor.</span></span> 

<span data-ttu-id="c974d-106">當使用者從類比裝置進行通話時，訊號和媒體會透過 ATA (電話轉接器) SBC。</span><span class="sxs-lookup"><span data-stu-id="c974d-106">When a user makes a call from an analog device, the signaling and media flow through the Analog Telephony Adapter (ATA) to the SBC.</span></span>  <span data-ttu-id="c974d-107">SBC 會根據內部路由Microsoft Teams，將電話傳送至 (網或公用交換電話網絡) PSTN。</span><span class="sxs-lookup"><span data-stu-id="c974d-107">The SBC sends the call to a Microsoft Teams endpoint or to the Public Switched Telephone Network (PSTN) based on the internal routing table.</span></span>  <span data-ttu-id="c974d-108">當裝置進行通話時，其路由取決於為裝置所建立路由策略。</span><span class="sxs-lookup"><span data-stu-id="c974d-108">When a device makes a call, the route it takes depends on the routing policies created for the device.</span></span>

<span data-ttu-id="c974d-109">在下列圖表中，直接路由已進行配置，因此任何 Teams 之間與 +1425 4XX XX XX 和 +1425 5XX XX XX 之間的號碼，都必須使用紅色路由 (虛線) ， 與 +1425 4XX XX XX 和號碼範圍 +1425 5XX XX 以外的任何其他號碼之間的任何 PSTN 通話，都必須使用藍色 (實線) 。</span><span class="sxs-lookup"><span data-stu-id="c974d-109">In the following diagram, Direct Routing is configured so that any Teams calls to and from the numbers between +1425 4XX XX XX and +1425 5XX XX XX must take the red route (dotted line), and any PSTN call to and from numbers between +1425 4XX XX XX and any other number except number range +1425 5XX XX XX must take the blue route (solid line).</span></span> 

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c974d-110">![顯示直接路由配置的圖表](media/direct-routing-analog-device.png)</span><span class="sxs-lookup"><span data-stu-id="c974d-110">![Diagram showing Direct Routing configuration](media/direct-routing-analog-device.png)</span></span>

## <a name="example--how-to-configure-the-use-of-analog-devices-with-direct-routing"></a><span data-ttu-id="c974d-111">範例：如何設定使用直接路由的類比裝置</span><span class="sxs-lookup"><span data-stu-id="c974d-111">Example:  How to configure the use of analog devices with Direct Routing</span></span>

<span data-ttu-id="c974d-112">若要設定使用直接路由的類比裝置，您必須將類比電話轉接器連接到 SBC，並設定 SBC 以使用直接路由。</span><span class="sxs-lookup"><span data-stu-id="c974d-112">To configure the use of analog devices with Direct Routing, you must connect the Analog Telephony Adapter to the SBC, and configure the SBC to work with Direct Routing.</span></span> 

<span data-ttu-id="c974d-113">此範例會逐步引導您完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="c974d-113">This example walks you through the following steps:</span></span>

1. <span data-ttu-id="c974d-114">連線 SBC 到直接路由。</span><span class="sxs-lookup"><span data-stu-id="c974d-114">Connect the SBC to Direct Routing.</span></span>
2. <span data-ttu-id="c974d-115">建立 PSTN 使用量。</span><span class="sxs-lookup"><span data-stu-id="c974d-115">Create the PSTN Usage.</span></span>
3. <span data-ttu-id="c974d-116">建立語音路由，並將其與 PSTN 使用量建立關聯。</span><span class="sxs-lookup"><span data-stu-id="c974d-116">Create a voice route and associate it with the PSTN Usage.</span></span>
4. <span data-ttu-id="c974d-117">將語音路由指派給 PSTN 使用量。</span><span class="sxs-lookup"><span data-stu-id="c974d-117">Assign the voice route to the PSTN Usage.</span></span>
5. <span data-ttu-id="c974d-118">啟用線上使用者。</span><span class="sxs-lookup"><span data-stu-id="c974d-118">Enable the online user.</span></span>
6. <span data-ttu-id="c974d-119">指派語音路由策略給使用者。</span><span class="sxs-lookup"><span data-stu-id="c974d-119">Assign the voice route policy to the user.</span></span>
7. <span data-ttu-id="c974d-120">建立類比裝置的聲音路由。</span><span class="sxs-lookup"><span data-stu-id="c974d-120">Create a voice route for an analog device.</span></span>

<span data-ttu-id="c974d-121">若要瞭解如何將 ATA 連接到 SBC 並設定 SBC，請參閱您的 SBC 製造商設定指南：</span><span class="sxs-lookup"><span data-stu-id="c974d-121">For information on how to connect an ATA to an SBC and configure the SBC, see your SBC manufacturer configuration guide:</span></span>

- [<span data-ttu-id="c974d-122">AudioCodes 組組檔</span><span class="sxs-lookup"><span data-stu-id="c974d-122">AudioCodes configuration documentation</span></span>](https://www.audiocodes.com/media/14278/connecting-audiocodes-sbc-with-analog-device-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf)

- [<span data-ttu-id="c974d-123">功能區組組檔</span><span class="sxs-lookup"><span data-stu-id="c974d-123">Ribbon configuration documentation</span></span>](https://support.sonus.net/display/UXDOC81/Connect+SBC+Edge+to+Microsoft+Teams+Direct+Routing+to+Support+Analog+Devices)
- [<span data-ttu-id="c974d-124">Oracle 組組檔</span><span class="sxs-lookup"><span data-stu-id="c974d-124">Oracle configuration documentation</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams)

## <a name="step-1--connect-the-sbc-to-direct-routing"></a><span data-ttu-id="c974d-125">步驟 1。</span><span class="sxs-lookup"><span data-stu-id="c974d-125">Step 1.</span></span>  <span data-ttu-id="c974d-126">連線 SBC 到直接路由</span><span class="sxs-lookup"><span data-stu-id="c974d-126">Connect the SBC to Direct Routing</span></span>

<span data-ttu-id="c974d-127">下列命令會設定 SBC 連接，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c974d-127">The following command configures the SBC connection as follows:</span></span>

- <span data-ttu-id="c974d-128">FQDN sbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="c974d-128">FQDN sbc.contoso.com</span></span>
- <span data-ttu-id="c974d-129">訊號埠 5068</span><span class="sxs-lookup"><span data-stu-id="c974d-129">Signaling port 5068</span></span>
- <span data-ttu-id="c974d-130">媒體旁路模式</span><span class="sxs-lookup"><span data-stu-id="c974d-130">Media bypass mode</span></span>
- <span data-ttu-id="c974d-131">已轉往 SBC 的通話記錄資訊-</span><span class="sxs-lookup"><span data-stu-id="c974d-131">Call history information forwarded to the SBC-</span></span>
- <span data-ttu-id="c974d-132">P-已確認身分識別 (PAI) 頁標題與通話一起轉轉</span><span class="sxs-lookup"><span data-stu-id="c974d-132">P-Asserted-Identity (PAI) header forwarded along with the call</span></span> 

```powershell
PS C:\> New-CsOnlinePSTNGateway -FQDN sbc.contoso.com -SIPSignalingPort 5068 -ForwardCallHistory $true -ForwardPAI $true -MediaBypass $true -Enabled $true 
```

## <a name="step-2--create-the-pstn-usage"></a><span data-ttu-id="c974d-133">步驟 2：建立 PSTN 使用量</span><span class="sxs-lookup"><span data-stu-id="c974d-133">Step 2:  Create the PSTN usage</span></span> 

<span data-ttu-id="c974d-134">下一個命令會建立一個空的 PSTN 使用量。</span><span class="sxs-lookup"><span data-stu-id="c974d-134">The next command creates an empty PSTN usage.</span></span> <span data-ttu-id="c974d-135">線上 PSTN 使用量是用於通話授權的字串值。</span><span class="sxs-lookup"><span data-stu-id="c974d-135">Online PSTN usages are string values that are used for call authorization.</span></span> <span data-ttu-id="c974d-136">線上 PSTN 使用方式會連結線上語音策略至路由。</span><span class="sxs-lookup"><span data-stu-id="c974d-136">An online PSTN usage links an online voice policy to a route.</span></span> <span data-ttu-id="c974d-137">此範例會將字串「Interop」新加到目前的可用 PSTN 使用狀況清單中。</span><span class="sxs-lookup"><span data-stu-id="c974d-137">This example adds the string "Interop" to the current list of available PSTN usages.</span></span> 

```powershell
PS C:\> Set-CsOnlinePstnUsage -Identity global -Usage @{add="Interop"} 
```

## <a name="step-3--create-a-voice-route-and-associate-it-with-the-pstn-usage"></a><span data-ttu-id="c974d-138">步驟 3：建立語音路由，並將其與 PSTN 使用量建立關聯：</span><span class="sxs-lookup"><span data-stu-id="c974d-138">Step 3:  Create a voice route and associate it with the PSTN usage:</span></span>

<span data-ttu-id="c974d-139">此命令會為號碼範圍 +1425 XXX XX XX 建立身分識別 「類比交互操作」的新線上語音路由。</span><span class="sxs-lookup"><span data-stu-id="c974d-139">This command creates a new online voice route with the identity “analog-interop” for the number range +1425 XXX XX XX.</span></span>  <span data-ttu-id="c974d-140">語音路由適用于線上閘道清單 sbc.contoso.com 將路由與線上 PSTN 使用方式「Interop」關聯。</span><span class="sxs-lookup"><span data-stu-id="c974d-140">The voice route is applicable to a list of online gateways sbc.contoso.com and associates the route with online PSTN usage “Interop”.</span></span> <span data-ttu-id="c974d-141">語音路由包含一個正則運算式，用來識別哪些電話號碼會透過給定的語音路由路由：</span><span class="sxs-lookup"><span data-stu-id="c974d-141">A voice route includes a regular expression that identifies which phone numbers will be routed through a given voice route:</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(425)(\d{7})$" -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="step-4-assign-the-voice-route-to-the-pstn-usage"></a><span data-ttu-id="c974d-142">步驟 4：將語音路由指派給 PSTN 使用量：</span><span class="sxs-lookup"><span data-stu-id="c974d-142">Step 4: Assign the voice route to the PSTN usage:</span></span>

<span data-ttu-id="c974d-143">此命令會使用身分識別 「AadiInteropPolicy」建立新的線上每個使用者語音路由策略。</span><span class="sxs-lookup"><span data-stu-id="c974d-143">This command creates a new online per-user voice routing policy with the Identity “AnalogInteropPolicy”.</span></span> <span data-ttu-id="c974d-144">此政策會指派單一線上 PSTN 使用量：「Interop」。</span><span class="sxs-lookup"><span data-stu-id="c974d-144">This policy is assigned a single online PSTN usage: “Interop”.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoutingPolicy -Identity "AnalogInteropPolicy" -Name "AnalogInteropPolicy" -OnlinePstnUsages "Interop"
```

## <a name="step-5-enable-the-online-user"></a><span data-ttu-id="c974d-145">步驟 5：啟用線上使用者</span><span class="sxs-lookup"><span data-stu-id="c974d-145">Step 5: Enable the online user</span></span>

<span data-ttu-id="c974d-146">此命令會使用身分識別選項修改 exampleuser@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c974d-146">This command modifies the user account with the Identity exampleuser@contoso.com.</span></span> <span data-ttu-id="c974d-147">在這種情況下，帳戶會修改為啟用 企業語音 ，即 Microsoft VoIP 的實現，且已啟用語音信箱，並將號碼 +142550000000 指派給此使用者。</span><span class="sxs-lookup"><span data-stu-id="c974d-147">In this case, the account is modified to enable Enterprise Voice, the Microsoft implementation of VoIP, with enabled voice mail and assigns the number +14255000000 to this user.</span></span>  <span data-ttu-id="c974d-148">此命令應針對每個使用者執行Teams， (公司租使用者中的 ATA 裝置) 使用者除外。</span><span class="sxs-lookup"><span data-stu-id="c974d-148">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Set-CsUser -Identity "exampleuser@contoso.com" -EnterpriseVoiceEnabled $True -HostedVoiceMail $True -OnPremLineUri "tel:+14255000000"
```

## <a name="step-6-assign-the-voice-route-policy-to-a-user"></a><span data-ttu-id="c974d-149">步驟 6：將語音路由策略指派給使用者</span><span class="sxs-lookup"><span data-stu-id="c974d-149">Step 6: Assign the voice route policy to a user</span></span>

<span data-ttu-id="c974d-150">此命令會指派每個使用者的線上語音路由策略AdisInteropPolicy給具有身分識別 exampleuser@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="c974d-150">This command assigns the per-user online voice routing policy AnalogInteropPolicy to the user with the identity exampleuser@contoso.com.</span></span>  <span data-ttu-id="c974d-151">此命令應針對每個使用者執行Teams， (公司租使用者中的 ATA 裝置) 使用者除外。</span><span class="sxs-lookup"><span data-stu-id="c974d-151">This command should be run for each Teams user (excluding ATA device users) in the company tenant.</span></span>

```powershell
PS C:\> Grant-CsOnlineVoiceRoutingPolicy -Identity "exampleuser@contoso.com" -PolicyName "AnalogInteropPolicy" 
```

## <a name="step-7--create-a-voice-route-for-an-analog-device"></a><span data-ttu-id="c974d-152">步驟 7：為類比裝置建立語音路由</span><span class="sxs-lookup"><span data-stu-id="c974d-152">Step 7:  Create a voice route for an analog device</span></span>

<span data-ttu-id="c974d-153">此命令會針對適用于線上閘道清單的號碼範圍 +1425 4XX XX XX 建立身分識別 「類比交互操作」的線上語音路由 sbc.contoso.com 並關聯到線上 PSTN 使用方式「Interop」。</span><span class="sxs-lookup"><span data-stu-id="c974d-153">This command creates an online voice route with identity “analog-interop” for number range +1425 4XX XX XX applicable to a list of online gateways sbc.contoso.com and associates it with online PSTN usage “Interop”.</span></span>  <span data-ttu-id="c974d-154">此命令應針對每個具有適當電話號碼模式的類比裝置執行。</span><span class="sxs-lookup"><span data-stu-id="c974d-154">This command should be run for each analog device with appropriate phone number pattern.</span></span> <span data-ttu-id="c974d-155">或者，在前一個步驟中，在配置線上語音路由時，可以使用適當的類比裝置數位模式。</span><span class="sxs-lookup"><span data-stu-id="c974d-155">Alternatively, a proper number pattern for analog devices can be used while configuring the online voice route during one of the previous steps.</span></span>

```powershell
PS C:\> New-CsOnlineVoiceRoute -Identity analog-interop -NumberPattern "^\+1(4254)(\d{6})$"  -OnlinePstnGatewayList sbc.contoso.com -Priority 1 -OnlinePstnUsages "Interop"
```

## <a name="considerations"></a><span data-ttu-id="c974d-156">考量</span><span class="sxs-lookup"><span data-stu-id="c974d-156">Considerations</span></span>

- <span data-ttu-id="c974d-157">除非另有說明，否則類比裝置是可傳送 DTMF 位數進行通話的任何裝置。</span><span class="sxs-lookup"><span data-stu-id="c974d-157">Unless otherwise note, an analog device is any device that can send DTMF digits to place a call.</span></span> <span data-ttu-id="c974d-158">例如，類比電話、傳真機和高空傳呼機。</span><span class="sxs-lookup"><span data-stu-id="c974d-158">For example, analog phones, fax machines, and overhead pagers.</span></span>

- <span data-ttu-id="c974d-159">連接到 ATA 的類比電話無法從 Teams。</span><span class="sxs-lookup"><span data-stu-id="c974d-159">Analog phones connected to an ATA are not searchable from Teams.</span></span> <span data-ttu-id="c974d-160">Teams使用者必須手動輸入與裝置相關聯的電話號碼，才能撥打該裝置。</span><span class="sxs-lookup"><span data-stu-id="c974d-160">Teams users must manually enter the phone number associated with the device to call that device.</span></span>  
 

## <a name="see-also"></a><span data-ttu-id="c974d-161">另請參閱</span><span class="sxs-lookup"><span data-stu-id="c974d-161">See also</span></span>

[<span data-ttu-id="c974d-162">規劃直接路由</span><span class="sxs-lookup"><span data-stu-id="c974d-162">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="c974d-163">設定直接路由</span><span class="sxs-lookup"><span data-stu-id="c974d-163">Configure Direct Routing</span></span>](direct-routing-configure.md)
