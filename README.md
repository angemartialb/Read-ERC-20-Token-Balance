import { ethers } from "ethers";

const RPC = "https://mainnet.base.org";
const TOKEN = "0xTokenAddress";
const WALLET = "0xYourWallet";

const ABI = [
  "function balanceOf(address owner) view returns (uint256)"
];

async function main() {
  const provider = new ethers.JsonRpcProvider(RPC);
  const contract = new ethers.Contract(TOKEN, ABI, provider);

  const balance = await contract.balanceOf(WALLET);

  console.log("Token balance:", balance.toString());
}

main();
