export default async (req) => {
  const ua = req.headers.get("user-agent") || ""

  if (!ua.startsWith("Roblox")) {
    return new Response("❌ ACESSO NEGADO — use um executor de Roblox", { status: 403 })
  }

  const realScript = await fetch("https://pastefy.app/fThaoDik/raw")
  return new Response(await realScript.text(), { status: 200, headers: { "Content-Type": "text/plain" } })
}
