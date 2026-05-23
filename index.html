// ============================================================
// IDAX Anthropic API Proxy — Cloudflare Worker
//
// SETUP (2 minutes):
// 1. Go to workers.cloudflare.com — create a free account
// 2. Click "Create application" → "Create Worker"
// 3. Delete the default code and paste this entire file
// 4. Click "Deploy"
// 5. Copy your worker URL (e.g. https://idax-proxy.YOUR-NAME.workers.dev)
// 6. In idax_parking_scoper.html find:
//      var ANTHROPIC_PROXY = '';
//    and replace with:
//      var ANTHROPIC_PROXY = 'https://idax-proxy.YOUR-NAME.workers.dev';
//
// ENVIRONMENT VARIABLE (required):
// After deploying, go to Settings → Variables → Add variable:
//   Name:  ANTHROPIC_API_KEY
//   Value: your Anthropic API key (get from console.anthropic.com)
// ============================================================

export default {
  async fetch(request, env) {

    // Handle CORS preflight
    if (request.method === 'OPTIONS') {
      return new Response(null, {
        headers: {
          'Access-Control-Allow-Origin': '*',
          'Access-Control-Allow-Methods': 'POST, OPTIONS',
          'Access-Control-Allow-Headers': 'Content-Type',
          'Access-Control-Max-Age': '86400',
        }
      });
    }

    if (request.method !== 'POST') {
      return new Response('Method not allowed', { status: 405 });
    }

    try {
      const body = await request.json();

      const response = await fetch('https://api.anthropic.com/v1/messages', {
        method: 'POST',
        headers: {
          'Content-Type': 'application/json',
          'x-api-key': env.ANTHROPIC_API_KEY,
          'anthropic-version': '2023-06-01',
        },
        body: JSON.stringify(body),
      });

      const data = await response.json();

      return new Response(JSON.stringify(data), {
        status: response.status,
        headers: {
          'Content-Type': 'application/json',
          'Access-Control-Allow-Origin': '*',
        }
      });

    } catch (err) {
      return new Response(JSON.stringify({ error: err.message }), {
        status: 500,
        headers: {
          'Content-Type': 'application/json',
          'Access-Control-Allow-Origin': '*',
        }
      });
    }
  }
};
